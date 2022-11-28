# Panel Exam Script

**SLIDE 1 (Hussein)**

hello everyone, my name is Hussein, and this is x1, x2 and x3 and we are the team behind PharmaBox. Our goal is to improve the pharmaceutical prescription pickup experience for both practitioners and patients in Canada.

**SLIDE 2 (Hussein)**

**SLIDE 3 (Hussein)**

let’s talk a little bit about the problem space. From the patient side, Canadians have picked up over 600 million prescriptions in 2016. With the increase in population, and ever-growing need for medications, it is most likely that there are more pickups in the current day. The issue behind picking up prescriptions is the wait time accompanied with it. This is typically induced by medication preparation times, and other factors. In surveys we’ve conducted over the term, most patients wait over 16 minutes to pick up their prescriptions.

**SLIDE 4 (Hussein)**

So, for some perspective there are over 11 thousand pharmacies across Canada and over 40 thousand licensed pharmacists.

**SLIDE 5 (Hussein)**

From the pharmacists’ perspective, there is currently a national shortage of pharmacists. With some health policy changes, these pharmacists are also experiencing an increase in workload. After surveying pharmacists this term, a large portion of pharmacists believe they spend a lot of their time doing clerical work.

**SLIDE 6**

**SLIDE 7**

The motivation for building this solution comes from the stats that represent the problem space. To summarize:

- Wait times for patients are long
- The increasing shortage of pharmacists and their increasing workload will continue to lengthen these wait times for patients
- Consequence of this are limited accessibility of patient care, and a lack of awareness by patients of services that pharmacies actually offer
- One of the statistics we came across that encouraged us to tackle this challenge, is the fact that there are opportunities to improve. 75% of prescriptions are repeat. Furthermore pharmacists are responsible for customer service tasks, which eat into the time they have to perform all their OTHER tasks

**SLIDE 8**

Some of the solutions we found when conducting our initial research of the problem space are displayed on this slide.

The first would be automated dispensing machines.

These are computerized drug storage and dispensing device used in the health care settings like hospitals and nursing homes. This solution still requires significant work by the pharmacist. The solution is also incredibly costly, and there’s a high magnitude of change required, making it not ideal for wide-spread adoption in pharmacies.

The second solution we came across was a pharmacy kiosk, which is ultimately allows for automated pharmacy pickup. An initial analysis of the solution revealed that the user experience is suboptimal, the authentication system is bulky and time-consuming, and the user interface is outdated. Furthermore, the system is only available in the US and isn’t currently adapted to the Canadian healthcare system.

**SLIDE 9**

With the solution we develop, we aim to improve both the patient and pharmacists experience. The objective of our project is develop an end-to-end product that will help reduce patient wait times, and pharmacists workload. We’ll do this by eliminating unnecessary patient interactions such as eliminating in-person instructions on repeat consumers, automating prescription pick-up when safe.

**SLIDE 10**

Implementing our solution in Canadian pharmacies will result in staff being able to service and interact with more patients in a day…..

- Improve care for patients who require more attention from pharmacists
- Pharmacists can take on other responsibilities to reduce the load of other healthcare staff

**SLIDE 11 - User Research Patients (Sammy)**

- We received responses from close to 2,905 respondents which exceeded our expectations
- Largest cohort was those aged 21-35
- Smallest cohort those aged 65+
- This was likely because we sent our the survey via platforms like LinkedIn, and placed posters around campus. Older adults are less likely to use these platforms or methods
- To address this disparity, population weights were normalized.

**SLIDE 12 - User Research Patients (Sammy)**

- When patients were asked how likely they are to use a remote prescription pickup service, more than 50% said they would try the service.
- This graph represents the probability that a member of a particular cohort would be very likely, likely, somewhat likely, unlikely, or would never use the service.
- We can see by summing across the positive likelihoods that the majority of users would be likely or greater to use the service.
- Encouraging given the little amount of information available and the tendency of individuals to avoid extremes
- Important to note that about 70% of customer service at pharmacies is repeat prescription refill, so even if those 65+ never used the pickup box service, the impact would still be substantial and these users would still stand to benefit from the service because it would reduce pharmacy wait times

**Slide 13 - User Research Pharmacy Staff (Josh)**

From our surveys with over 50 pharmacists we gained valuable insights into how they spend their time at work.

- A large portion of the time is spent filling refill prescriptions
- Pharmacists are the first point of contact for medication-related advice for patients

**Slide 14 - User Research: Wait times (Josh)**

When asked about wait times, we found:

- Half reported average wait times to be 16 minutes or more
- With a large majority saying peak wait times to be over 16 minutes
- Returning patients have to wait a long time for repeat service
- New patients have to wait long to get questions answered
- Pharmacists have to deal with impatient patients

**Slide 15 - Average Wait Times: Expected Versus Actual Reported (Josh)**

How do these insights translate into design requirements:

- Patients reported acceptable wait times to be between 6 and 9 minutes.
- We’ve selected 6 minutes as the benchmark for the PharmaBox pickup time
- Returning patients and new patients don’t have to compete for pharmacists time, each party is satisfied.

**Slide 16 - (Transition)**

**Slide 17 - Application Architecture (Josh)**

Going over a high level overview of the application architecture:

- The patients and pharmacist interact with a web app optimized for desktop and mobile usage
- User authentication and password storage is handled by Clerk
- This tool allows pharmacist to:
  - Create prescription notifications
  - Manage staff members
  - And in the future, create custom pickup workflows
- Patients can access:
  - Their previous prescription pick ups
  - QR codes to access active prescriptions
- This is enabled through a backend and API hosted on `Vercel`
- Database hosted on AWS in Montreal for future HIPA compliance
- Lastly the hardware
  - Raspberry Pi which is a small computer capable of controlling door locks as well as communicate with server
  - Sync locker-box state with our backend
  -

**SLIDE 18 - Pharmacist Dashboard Demo (Sammy)**

- The dashboard LFP is the first thing that pharmacists and pharmacy technicians will see when they login or access the application
- It is designed to serve as a dashboard and cover the 80/20 workflow process.
- On the dashboard pharmacists can currently create prescriptions by searching for a patient, adding a description, adding a cost and choosing a locker. We plan on streamlining this process by introducing auto-locker selection and other optimizations in later iterations such as hotkeys for super-users and so on.
- Staff can also monitor prescriptions that are awaiting pickup as well as the status of locker boxes.

**SLIDE 19 - Pharmacist Dashboard LFP Demo (Sammy)**

- We can see the process followed for creating a prescription that the LFP follows. In the future we want to streamline this process, for example, importing directly from pharmacy management software
- Administrators can manage their team, and view patients
- Administrators can add team members, or remove them. Team members can only view other team members
- We will also be building a workflow management system that was not included in the LFP so that pharmacies can customize their workflows, and a logbook to keep track of all operations for internal and regulatory compliance.

**SLIDE 20 - (Hussein)**

- Explain what patients see
- Ability to create an account
- Must opt into service and provide birthday for verification
- See past prescriptions and current ones that need to be picked up
- Can open QR code to open up a locker-box for a certain prescription

**SLIDE 21**

**SLIDE 22 (Hardware Demo)**

- 5MP Camera to scan QR codes
- Raspberry Pi
- Solenoid + Relay
- LCD

**SLIDE 23**

**SLIDE 24**

- The user testing we performed on the low fidelity prototype revealed insights that will guide future prototype iterations. First, we found that the average time to open PharmaBox is just 15 seconds. This is significantly lower than the average wait times in pharmacies.
- User’s confusion when scanning their QR codes to interact with the box revealed that more instructions were needed at this step, and explicit directions should be added to the Locker box in the next design cycle.

**SLIDE 25**

**SLIDE 26 Pharmacist Testing Plan (Sammy)**

- We are currently in discussion with the Mr. Patel, the pharmacist at the campus pharmacy to find a time when we can conduct user testing with pharmacists.
- This is challenging given their busy schedule and the stress that healthcare workers are already experiencing (a game of email tag), we do not want to add to, or disrupt their workload
- We hope to validate and evaluate our pharmacist workflow by conducting task-based used testing with pharmacists and capture their feedback. Their feedback is critical to the next design iteration of both the web interface and the physical box, specifically prescription loading processes.

**SLIDE 27 Closing (Sammy)**

- Thank you, Question period

**SLIDE 28**

**SLIDE 29**
