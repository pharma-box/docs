# Low Fidelity Prototype

_LFP Decision Journal_

## Pharmacy Service Integration

During our team meeting on Tuesday October 11th 2022 We discussed the approach we would take towards integration with existing pharmacy solutions and services that exist on the market and how this would play into our vision as a _platform-as-a-service_ solution to prescription pickup. We quickly realized that [Kroll by Telus Health](https://www.telus.com/en/health/health-professionals/pharmacies/kroll) is the main large player when it comes to pharmacy management software in Canada. in fact [Kroll](https://www.telus.com/en/health/health-professionals/pharmacies/kroll) occupies about **90%** of the market. However what Kroll doesn't do is handle point-of-sale transactions. It only deals with management of medication, insurance, patient info and so on. As a result pharmacies generally use their own POS (point-of-sale) systems. This means that PharmaBox does not need to worry about payment integration directly with Kroll, but can do so on a customer-specific basis, i.e via a platform like [Stripe](https://stripe.com/en-ca).

It also means that the only information we need from [Kroll](https://www.telus.com/en/health/health-professionals/pharmacies/kroll) is the outstanding balance on the prescription, and information about the patient that could be used to verify a patients identity. The good news is that getting this information is [possible](https://www.syscreations.ca/blog/kroll-patient-data/), the bad news is that it is hard because Kroll does not appear to have a dedicated API and it is enterprise software. This means that unless we are an actual pharmacy, we can't really get a hold of it.

To get around this, we are planning to `mock` out the functionality we would expect from a system like Kroll in the long term. In the short term however we will implement an interface, to allow pharmacists and pharmacy technicians to export patient information into the PharmaBox system, or give them the ability to manually input it via a sort of form. This will all be backed up via the same `API` so the possibility of integration remains on the table in the future.

## Basic Infrastructure

To-date, we believe that our application will consist of the **PharmaBox** as the actual hardware and medication storage component, a **Web Client** consisting of a customer-facing application, and an admin-side web interface. The customer-facing application will be a web application embedded in a mobile application, as well as a mobile friendly website. This is where users will be able to register for the service and make payments.

These services will all be connected via an **API Layer** that will integrate a **Business Logic Backend**, a **Payments Service** and a **Mock Pharmacy Management Service** with the frontend clients. Information will be stored in a set of databases, likely hosted on **Amazon Web Service**. AWS was chosen because it is relatively cheap for the kind of compute we require, it has nice role management systems, the team has experience using AWS from the past, and we have $500 of compute credit with AWS.

We need to decide between a number of possible solutions for our backend these are:

- AWS Elastic Beanstalk
- AWS DynamoDB with Clients hosted on S3, managed by `Docker` with `Kubernetes`, auth with AWS `Cognito`
- AWS RDS with Clients hosted on S3, managed by `Docker` with `Kubernetes`, auth with AWS `Cognito`
- AWS Amplify with RDS or DynamoDB

We also need to discuss:

- REST API or `GraphQL`?

The general consensus is that the frontend will be written with `React` and embedded in a mobile application with `React Native` as needed. Right how `Next.js` is a leading candidate for the development since it has `API` routing an webpage routing built in. It also renders on the server making it very performant. However this is still up for discussion. The backend will likely be written in `Node.js` because of its simple API quick ramp-up time.

Hardware code is likely to be `Python` and utilize a `Raspberry PI` although exact hardware specifications are still in progress.

Look into what ideal user flows look like for pharmacists and patients. What are our Key Performance Metrics? How do we want to minimize friction and make the interactions as quick as possible in order to incentivize the usage of Pharmabox? What roadblocks and challenges are preventing us from doing that?
