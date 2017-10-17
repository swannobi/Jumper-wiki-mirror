# Third Party Developer Program Proposal

## Table of Contents
- [Purpose](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#purpose)
- [Goals](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#goals)
- [Proposed Additions](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#proposed-additions)
- [Projection](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#projection)
- [Implementations](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#implementations)
    - [Repository Template](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#repository-template)
    - [Quality Assurance](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#qa)
    - [Documentation and Guides](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#documentation-and-guides)
    - [FAQ](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#faq)
- [Approval Process](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#approval-process)
    - [Part One](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#part-one)
    - [Part Two](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#part-two)
- [Issues to Watch](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#issues-to-watch)
    - [Over-saturation](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#over-saturation)
    - [Complacency](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#complacency)
- [Red Portal](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#red-portal)


***

## Purpose

To revise the current third party repository system and establish a clear, concise, and well documented approval process through the use of subject matter experts under the oversight of the core developer team.

## Goals  
* Stream-line the repository approval process      
* Remove the need to maintain a two list system on the docs  
* Prevent broken and malicious cogs from circulating  
* Promote diverse, high quality cog development  
* Remove arbitrary barriers of entry
* Establish a dedicated team of experts to manage the program  
* Provide guides, rules, and documentation on cog development  

## Proposed Additions

**Junior Cog Creator Role (Working Title)**
  * Entry level cog creator role    
  * (Does not need to have a color)        

**Senior Cog Creator (Working Title)**
  * Senior level cog creator role.
  * Should have a color    

**Cog QA (Working Title)**
  * Manages applications
  * Should have a color

## Projection

To accomplish all of the tasks within this document, it is estimated to take 1-2 weeks. This time can fluctuate up or down depending on the available free time everyone has available to work on these tasks, and any delays due to changes. Once everything is completed further changes will take less time to implement.

## Implementations

### Repository Template

There should be an easily obtainable template for how a repository should be setup. It should include, but is not limited to:
* A readme
  * Should have the repository name
  * Installation instructions
  * Provide credits
  * Contact details for bugs/issues/suggestions etc
* Correct info.json files
* At least three cogs ([See Exceptions](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft#quality-over-quantity))
* Cogs must be in it's own folder with it's own info.json file
* Requirements should be listed if any

For more information, use this [example template](https://github.com/Cog-Creators/Applications)

### QA

QA's sole purpose is to monitor, report, evaluate, and curate the cog creator process.
This role is not meant to divide or subjugate cog creators and should be viewed as a 
separate entity. QA members will be focused on providing continual 
support to applicants and alleviates the need for core developers to split their time
between writing code and monitoring/evaluating applications. QA can also be assigned to
tasks on the core project to provide core developers with high quality feedback on new
features. 

Members of this team will be chosen at the discretion of the core developers. 

**Qualities of a QA member should have most if not all of the following:**
* Great understanding of Python
* Non-confrontational attitude
* Willingness to help others
* Great testing skills
* Ability to provide constructive feedback

### Documentation and Guides

A revamped docs and guides section should be added to the red docs. It should walk the user through the application process. These docs and guidelines should be separate from cog making tutorials, which can be placed in a different category. This will serve as a great place to send people who are asking questions about how they can get involved in the community.

### FAQ

A Frequently asked question section should be added to cover common questions that is not covered in the documentation or guidelines. While the documentation is meant to instruct and inform, it is not all inclusive. The FAQ will cover the gaps missing and can stop us from repeating the same answer in support discussions.

## Approval Process

Two part system, junior and senior cog creators

### Part One

**Junior Level Cog Creators**

Junior cog creators have made it through the initial application process. They have shown that they can meet the minimum standards required to create content for the community. Junior level creators will also be able to add their repository on to the Red Portal. They will be required to send a commit feed (Implementation WIP) from their repo to discord so that QA may do random checks to ensure malicious code is not being uploaded. This feed is not meant to nitpick on coding styles!

**Junior Level Approval Process**
 
[See flow chart](https://cdn.discordapp.com/attachments/361910438507577359/364913616052289557/My_First_Document_-_Page_1.png) for a visual representation

A user will submit an issue to a proposed Repository Cog Creators/Applications. The user will then need to pass a number of basic requirements. These standards are lenient enough to not stifle developers but set a standard to ensure a good user experience when downloading third-party cogs. The process will involve the following steps:

* Application started as an issue on the Cog Creators/Application page
* Application assigned a QA team member
* Application reviewed on the following criteria:
    * Does NOT contain malicious code
    * Does NOT contain copied or stolen code
    * Does NOT conflict with core cogs/commands
    * People who work on a cog must be properly credited
    * Must disclose if your cogs have heavy CPU/memory/disk space usage
    * Must disclose if your cogs contain NSFW material
    * All commands are tested and return as expected
    * The code is NOT blocking
    * Repository is formmated correctly as [outlined](https://github.com/Cog-Creators/Applications)
    * No over saturation by similar cogs ([See exceptions](https://github.com/Redjumpman/Jumper-Cogs/wiki/Draft/_edit#over-saturation))
* Application approved or denied
* Issue is closed

Applicants who fail the process my reapply no earlier than one week's time. Typically this is to give the user the ability to further test/fix issues detailed by the QA member. Applicants who submit malicious code will be banned.  

### Part Two

**Senior Level Cog Creators**  
Senior level cog creators are previous junior level creators who have shown exponential growth and demonstrated a willingness to learn and communicate effectively. Senior level cog creators have passed the second application process which is much more strict on code quality and includes an emphasis on character and integrity. Senior level creators will no longer be subject to random screens for their commits. Cog creators will also be given a channel in the Cog Support server to provide dedicated support to their communities. They should also be granted access to the adv coding channel. In the future it is possible to allow this group to help manage the cog board. Senior cog creators should be more or less mentors to the junior level creators.

**Senior Level Approval Process**

A user will submit another issue to Cog Creators/Applications. This time the user will need to pass a much more strict set of standards. The application process steps are as follows:

* Submit application to Cog Creators/Applications
* Application assigned a QA Member
* Application reviewed based on the following criteria:
    * Code is PEP8 compliant
    * Code is not bloated or causing unnecessary stress
    * Code gracefully handles errors
    * Applicant is in good moral standing with the community
    * Applicant has 0 warnings within the last 6 months
    * Repository adds something new to the community
    * Applicant responds appropriately to criticism
    * Regularly active in the Red Support Server
    * Communicates with cog creators/core developer team
    * Positive attitude
* Application given a pass or fail
    * Time frame for re-submission based on QA's judgement
* Passed Applications requires majority vote from core developers.

## Issues to watch
I've highlighted some issues that we need to be wary of moving forward with this process.

### Quality over Quantity

Applications should not fail based solely on not having at least three cogs. This rule is meant for developers who are very new to programming to allow more time for focusing on honing their craft. Repositories that have less than three cogs should demonstrate some or all of the following qualities: uniqueness, creativity, and complexity. When looking at these qualities QA should ask the following questions:

* How unique is this cog? Are there any others like it on cog.red?

* How creative is the cog? How fun or useful is the cog?

* How complex is it? Does the size, feature-set, or utility dwarf most cogs?

### Over-saturation

We have to be wary of denying applications simply because another repository has something similar. Users need to have options. If the applicant can demonstrate how their cog is similar, but it provides additional utility it should be allowed. One or two people should not be allowed to have a monopoly on an idea and we should not reinforce that behavior.

### Complacency 

Repositories should not be left waiting for a response for weeks at at a time. If a no one on the QA team or just one person is responding to all the messages then they need to be demoted back down to a cog creator. This role's purpose is to serve the community, and if you aren't serving it then we need to allow other users to step up. 

## Red Portal
After speaking with Orels, there will be a version 3 of the Red Portal. This new backend will allow us to have people labeled as approved repositories while still allowing independent creators to add their repositories. This system will be automated, and supports allowing us to suspend a repository that is malicious or damaging. The new site will also include a safe mode (default) that hides the unapproved cogs from the list. Anytime a repository is added to the website a webhook will notify QA of the addition and allow us to check even the unapproved repositories for vulnerabilities. 
