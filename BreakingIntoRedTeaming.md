# Breaking Into Red Teaming
_June 4, 2022_

## Preface
This is my story of how I got into red teaming - from college, undergrad jobs, professional jobs, then finally the red team!

## College & Prep
I obtained a bachelor + master in a technical/business field and worked various jobs throughout college that helped me gain experience in code development, systems integration, customer experience and security review. This split-focused degree was valuable to me because it helped me develop technical skills that I can hack with, but also business skills that I can use in a professional environment. Working during school was critical to me developing hands-on and real-world experience and teamwork and how to work in a company-environment. Elective courses and security-focused projects were also very helpful in allowing me to get a taste of what security is as I narrowed down my career choice.

### Technical skills
This is a no-brainer. If you want to hack, then you need to learn how things work and how to use, modify, and eventually create the tools of the trade. Starting off your schooling and career in a field like systems administration or software engineering can give you a strong foundation of basic technical knowledge that will enable faster and deeper understanding of security concepts and systems and environments down the road. Basic coding skills are very important as red teamers need to utilize public exploits and tools. Sys admin type knowledge is also handy when it comes to advanced exploitation and post exploitation (persistence, privilege escalation, lateral). Try to surround yourself with classes and jobs and friends that can help you develop the necessary security skills and try to find a mentor who you can bounce questions and advice off of.

### Business skills
In every professional role, there is always a customer - whether it's a paying person or company, or your own company itself. In red teaming, you're not coding a product, rather you’re providing a service. Part of your services will of course include hacking, but it's for specific reasons and objectives. Typically, at the end of each engagement or campaign, there is a report or readout to upper management. This is a critical part of being a red teamer - the ability to sway an audience. One of the major goals of red teaming is to inspire your customer to make systemic security improvements. Your end goal is NOT to file tickets, though you probably will. To master the art of persuasion, you'll need strong presentation or report-writing skills, depending how your company consumes reports or how you choose to deliver. Storytelling is another method of delivering your report, so get comfortable with speaking and presenting. 

Additionally, a basic understanding of how businesses operate will also help you better understand your customer and their needs. You could also think of your own red team as a business within your business - if you're an in-house red team. 

Key takeaway here: red teamers hack with a purpose and understanding how your work impacts a company is the driver of how you persuade change. 

## Early Career
Red teams and security roles in general are hard to get into right out of college. I think this is because of the base experience and knowledge that’s typically required to work proficiently and not break things. Security work often includes access to highly confidential data, so there’s higher risk when inexperienced interns and college grads start accessing systems and handling restricted data. In red teaming specifically, there’s a lot that can go wrong when emulating adversaries and hacking on major production targets, so more experience and trust is needed.

To break through the barriers I mentioned above, get as much experience and knowledge as possible in security-focused electives and projects/capstone. This will not only help you determine where you want your career to go but will also give you opportunities to try out security to see if it’s right for you.

Additionally, getting a few security certificates is also a good way to show that you’re serious about fine tuning your skills outside of normal schooling and work. It shows that you’re passionate about going above and beyond the average person. Remember, you’ll be competing for roles when you apply for programs and jobs. Perhaps start off with CompTIA Security+, or GIAC GSEC, then move up to CEH for example. OSCP would be a strong certificate for aspiring red teamers but it’s a bit more advanced for fresh students. It probably requires a few years of dedicated security study and experience before it would be worth attempting. 

Capture the Flag events like the SANS Kringle Cons or pentesting challenges like HackTheBox are another good way to practice your skills in a fun community. There are hints, support, and leaderboards to help keep you inspired and growing. It’s also an opportunity to network with other security professionals who may be looking for new hires. If you do these, try to document your progress write write-ups, even if they’re so-so quality (see next section).

The last thing I’ll mention is to have a public portfolio of work. Anything IT-related is okay (web dev, books you’ve read, IT service/presentations, projects), but security work is best. Perhaps start a GitHub repo of several simple bash scripts of common commands you run in CTFs, or a repo of HackTheBox walkthroughs, or make a few blog posts based on security research you’ve conducted (how to use C2, problems with Basic Auth, how buffer overflows work). What interests you and what will show off your passion and skills?

## Getting into Red Teaming
Understanding the difference between pentesting and red teaming is crucial at this point - you could very well be asked in an interview. There are lots of different opinions out there and lots of companies mix these two roles, but they're definitely not the same. Here are some of the main differences in my opinion:

**Penetration Testing**\
Penetration testers often focus on a particular app (domain, sourcecode, web app, api, etc). Their objective is typically to find as many bugs as possible and write up a report of findings. They often have a focus, like authentication/authorization checks. Pentests are typically compliance-driven, so scope is often restricted to ensure a cheap stamp of compliance approval is obtained.

**Red Teaming**\
Red teams emulate real-world adversaries to provide an independent, unbiased measurement of the security posture of a target from an adversarial perspective. The results will either confirm an organization's assumptions about their securitry, or they invalidate assumptions and inspire change. For example, BigCorp wants to know how safe they are against ransomware so they can appropriately allocate security funding, so they hire RedTeamsRUs to assess their current susceptibility. RedTeamsRUs then gets to be creative and essentially break into to anything within the established Rules of Engagement (no DDoS, corp servers only, etc). Because of a large scope and realistic emulation of adversaries, red teamers must be very creative and think and act like criminals in order to be succesful. In order to better measure real-world threats, red teams seek to emulate specific threat actor Tactics, Techniques, and Procedures (TTPs). See [Mitre Att&ck](https://attack.mitre.org) for example TTPs and attack chain.

### How to Prepare
There are tons of penetration testing books and courses, but not that many red teaming ones. Pentesting is a good start to make sure you're technically ready, but the red team mindset is a differentiating factor in a new hire prospect. Here are some must-reads to help you understand red teaming:
1. Red Team Development and Operations, by Joe Vest & James Tubberville
2. Red Team: How to Succeed By Thinking Like the Enemy, by Micah Zenko

