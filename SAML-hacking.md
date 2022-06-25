# SAML-hacking
Tips and tricks for hacking SAML SSO applications.

# SAML 101
Security Assertion Markup Language (SAML) is an XML-based, Single Sign-On (SSO) authentication flow between two parties: the Identity Provider (IDP) and the Service Provider (SP). The IDP (Okta, Auth0, etc) would be the central identity and authentication/authorization system that is connected to an org's ActiveDirecory for example. The SP would be the application providing the protected service that the end user is attempting to reach.

In a typical scenario, a user navigates to a protected application, the app redirects the user to the IDP, the user authenticates to the IDP, then the IDP returns a SAML Assertion to the user, which they then forward to the app to login. In order for the app to verify that the IDP has indeed authenticated the user, the app is *__supposed__* to validate the assertion's XML signatures - which would protect the assertion from tampering. _Hint hint..._

# Common Issues
Because of the complexity of SAML flows, app developers often make mistakes when writing their own SAML consumption code which can lead to XML signature bypass vulnerabilities. While SAML libraries are the right way to go, even they get it wrong sometimes too ([SimpleSAMLPHP](https://simplesamlphp.org/security/201911-01)).
Additionally, SP SAML ACS endpoints process IDP SAMl Assertion XML and can therefore have XXE vulnerabilities. This would happen before any authentication takes place.

## User Impersonation
__The Issue__\
SAML XML signature validation bypass can lead to impersonation of other app users.

__The Tip__\
Download a free copy of BurpSuite Community Edition and install the [SAML Raider](https://portswigger.net/bappstore/c61cfa893bb14db4b01775554f7b802e) plugin. It's got about 12 different SAML XML signature attacks including stripping signatures, signing assertions with your own self-signed keypair, and various XML Signature Wrapping (XSW) attack arrangements. As you craft the payloads in SAML Raider, try modifying the username in the assertion to impersonate antoher user. Be patient and try all the attacks - maybe one will get past app signature checks!

## Escalation of Privileges
__The Issue__\
As above, signature validation bypass allows tampering of SAML assertion contents. Often times, SAML assertions will contain not only the username of the user, but also additional attributes like role or other permissions-related attributes.

__The Tip__\
See the SAML Raider tip above, but instead of modifying the username, try modifying the user roles attributes.

## Injections
__The Issue__\
As above, signature validation bypass allows tampering of SAML assertion contents. In this case, however, we're looking for application logic that could insecurely include assertion attributes into the application code. For example, a username or first name attribute that is included in the front-end could result in XSS. Or if included in the backend, then SQL or LDAP or template injection could be exploited, etc. This of course depends on the application's languages and technologies in use.

    Welcome, minispooner<script>alert(1)</script>!


__The Tip__\
See SAML Raider tips above

## XXE in SAML ACS
__The Issue__\
Because SAML is XML-based, the application uses an XML parser called an Assertion Consumer Service (ACS) to consume SAML Assertions. Anytime XML is being processed, there's an opportunity for XXE injection.

__The Tip__\
Try XXE injections. The nice thing here is that the XML processing occurs before any SAML or signature validation, so it can be exploited pre-authentication, meaning we don't need any IDP signatures or valid SAML - just the XXE.

## Additional Resources
- [HackTricks](https://book.hacktricks.xyz/pentesting-web/saml-attacks) has gathered a lot of good data.
- [BurpSuite SAML Raider](https://portswigger.net/bappstore/c61cfa893bb14db4b01775554f7b802e)
- [Comments attack](https://developer.okta.com/blog/2018/02/27/a-breakdown-of-the-new-saml-authentication-bypass-vulnerability)
