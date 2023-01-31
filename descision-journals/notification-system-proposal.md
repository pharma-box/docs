# Notification System Proposal

## Proposal A: Twilio Sendgrid Email API:

- Using twilio sendgrid allows us to use the API to send 100 emails/day
  - This should be sufficient for our project’s purpose
- Cost is $0/month
- https://sendgrid.com/pricing/

Pros:

- Easy to integrate API
- Price is free
- Scalable solution if we want to go further with the project by changing account type to a different plan

Cons:

- We wont have a dedicated IP for now. Can be made available by upgrading plan in the future
- We must consider whether email is the best notification way?
- Adding in that API dependency

## Proposal B: Nodemailer library:

- If we use nodemailer library, it is unlimited emails
- No limit would be nice, might actually be easier to in
- https://nodemailer.com/about/

Pros:

- No fees
- Unlimited emails a month
- Easiest integration

Cons:

- Less customizable emails then twilio’s API service
- We must consider whether email is the best notification way?

## Proposal C: Twilio SMS API:

- We can send text notifications
- Two pricing plans:
  - One if sending just text
  - One with sending pic with text
- [https://www.twilio.com/sms](https://www.twilio.com/sms)

Pros:

- Everyone has their phone’s on them
  - Is this better then sending with email though?
- Easy to integrate with API
- Scalable

Cons:

- Pay as u go
  - 0.0079 USD for local to send text
  - 0.02 USD to send image local
- Adding in that API dependency

**Table 1 – Weighted Decision Matrix**

<table>
  <tr>
   <td rowspan="2" colspan="2" >
   </td>
   <td colspan="6" >
    Proposed Designs
   </td>
  </tr>
  <tr>
   <td colspan="2" >
    SendGrid API 
   </td>
   <td colspan="2" >
    Nodemailer library
   </td>
   <td colspan="2" >
    Twilio SMS
   </td>
  </tr>
  <tr>
   <td>
    <strong>Criteria</strong>
   </td>
   <td>
    Weight
   </td>
   <td>
    Rank
   </td>
   <td>
    Score
   </td>
   <td>
    Rank
   </td>
   <td>
    Score
   </td>
   <td>
    Rank
   </td>
   <td>
    Score
   </td>
  </tr>
  <tr>
   <td>
    <strong>Integration Complexity</strong>
   </td>
   <td>
    0.4
   </td>
   <td>
         2	
   </td>
   <td>
    0.8
   </td>
   <td>
    1
   </td>
   <td>
    0.4
   </td>
   <td>
    3
   </td>
   <td>
    1.2
   </td>
  </tr>
  <tr>
   <td>
    <strong>Cost</strong>
   </td>
   <td>
    0.2
   </td>
   <td>
    2
   </td>
   <td>
    0.4
   </td>
   <td>
    1
   </td>
   <td>
    0.2
   </td>
   <td>
    3
   </td>
   <td>
    0.6
   </td>
  </tr>
  <tr>
   <td>
    <strong>Scalability </strong>
   </td>
   <td>
    0.3
   </td>
   <td>
         2
   </td>
   <td>
    0.6
   </td>
   <td>
    3
   </td>
   <td>
    0.9
   </td>
   <td>
    1
   </td>
   <td>
    0.3
   </td>
  </tr>
  <tr>
   <td>
    <strong>Notification friendly</strong>
   </td>
   <td>
    0.1
   </td>
   <td>
    2
   </td>
   <td>
    0.2
   </td>
   <td>
    3
   </td>
   <td>
    0.3
   </td>
   <td>
    1
   </td>
   <td>
    0.1
   </td>
  </tr>
  <tr>
   <td>
    <strong>Total</strong>
   </td>
   <td>
    1
   </td>
   <td>
     
   </td>
   <td>
    2.0
   </td>
   <td>
     
   </td>
   <td>
    <strong>1.8</strong>
   </td>
   <td>
     
   </td>
   <td>
    2.2
   </td>
  </tr>
</table>

The lowest score is considered the most optimal which is depicted by integrating the NodeMailer library.
