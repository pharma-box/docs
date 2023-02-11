# Meeting Minutes February 1st 2023

Feb 1st 2023

1. Discuss Roles for design iterations
2. Choose a direction that we want to go in
3. ~~Settle on a testing plan for Campus Pharmacy~~

- We don’t need patients to sign up, pharmacy staff should just be able to add patients, ideally, this would happen via Kroll, but in the absence of the ability to integrate with Kroll, the information can be manually entered, or even added via CSV or something. To express that we could have integration, we can expose an endpoint for adding a user.

**First Design Iteration:**

- Improve LCD to have more explicit instructions ✅
- Patient add by CSV✅
- Remove Price Field
- Enter code via keypad sent via SMS ✅
- Store Pickup Time from door state ✅
- Allow the pharmacist to authorize the user for the day and display the authorized pharmacist. ✅

**Second Design Iteration:**

- Proper unlocking mechanism/self-unlocking hinge
- Lockerbox made of wood, proper screws + hinges ✅
- Be able to provide a report with time, who retrieved the prescription, what prescription etc., DIN,

**Tasks:**

1.  Add all of the tasks to Jira and then assign them appropriately
2.

**Roles**

1.  Aliya
    1. Patient add by CSV
    2. Lockerbox made of wood, etc
2.  Hussein 3. Find best SMS solution 4. Integrate SMS solution 5. Work on integration authentication of code with hardware?
3.  Joshua 6. Improve LCD instructions 7. Integrate keypad into the firmware 8. Lockerbox made of wood, etc 9. Store pickup time from door state
4.  Sammy 10. Need the ability of pharmacists to create a patient profile. This profile can be used at any pharmacy. To create a Patient: 1. Full Name 2. Phone Number 3. Date of Birth 11. Allow the pharmacist to authorize the user for the day and display the authorized pharmacist.

        This will require coordination with Hussein for the patient notifications
