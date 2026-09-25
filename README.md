# EXPERIMENT 4 - AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL

## OBJECTIVE

To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as user identity, event name, event time, AWS service, region, and operation status.

---

## REQUIREMENTS

* AWS Account
* Web Browser
* Internet Connection
* Amazon S3 Access
* AWS CloudTrail

---

# PART A - ACCESS AWS CLOUDTRAIL

## Step 1: Login to AWS

1. Open the AWS Management Console.
2. Sign in using your AWS account.
3. In the AWS search bar, type **CloudTrail**.
4. Select **AWS CloudTrail**.
<img width="1600" height="855" alt="WhatsApp Image 2026-09-25 at 4 39 55 PM" src="https://github.com/user-attachments/assets/e37d7c0c-2bed-41ce-a6ef-a4959ef252c6" />

---

## Step 2: Open Event History

1. In the CloudTrail navigation menu, select **Event history**.
2. CloudTrail displays recent AWS activity.
3. Review the available events.

The Event History page displays information such as:

* Event time
* Username
* Event name
* Event source
* Resource type
* Resource name
<img width="1600" height="848" alt="WhatsApp Image 2026-09-25 at 4 45 50 PM" src="https://github.com/user-attachments/assets/9a0dc253-61fe-439b-a6df-77f06cbe4834" />

---

# PART B - ANALYZE A CLOUDTRAIL EVENT

## Step 3: Select an Event

From the Event History list, an S3-related event was selected.

The event selected was:

**CreateBucket**

The event details were opened and analyzed.
<img width="1600" height="851" alt="WhatsApp Image 2026-09-25 at 4 48 25 PM" src="https://github.com/user-attachments/assets/619f75fd-b9f1-4229-8b7a-32c5443d507b" />
<img width="1600" height="851" alt="WhatsApp Image 2026-09-25 at 4 50 27 PM" src="https://github.com/user-attachments/assets/767bc011-d711-4c45-bc9c-543d79d503c1" />

---


## Step 4: Analyze the CreateBucket Event

The **CreateBucket** event indicates that an Amazon S3 bucket creation operation occurred.

| Parameter | Observation |
|---|---|
| **Event Time** | September 25, 2026, 16:56:54 (UTC+05:30) |
| **User Name** | root |
| **Event Name** | CreateBucket |
| **Event Source** | s3.amazonaws.com |
| **AWS Region** | eu-north-1 |
| **Read-only** | false |
| **Error Code** | - |
| **Activity** | S3 bucket creation |

### Meaning of Important Fields

| Field | Meaning |
|---|---|
| **Event Time** | Time at which the activity occurred |
| **User Name** | User or identity associated with the activity |
| **Event Name** | AWS operation that was performed |
| **Event Source** | AWS service that generated the event |
| **AWS Region** | Region where the activity occurred |
| **Read-only** | Indicates whether the event was only a read operation or involved a change |
| **Error Code** | Indicates whether an error occurred during the operation |
<img width="1600" height="846" alt="WhatsApp Image 2026-09-25 at 4 54 19 PM" src="https://github.com/user-attachments/assets/c602d6be-39b9-4e7f-9788-6f7938bb8ee5" />

---

# PART C - IDENTIFY ANOTHER CLOUDTRAIL EVENT

## Step 5: Select Another Event

1. Return to **CloudTrail → Event history**.
2. Select another event.
3. Open its details.
4. Record the important fields.

The second event selected was:

**AutomatedDefaultVpcCreation**

This event is associated with **Amazon EC2** and represents automated creation of the default VPC infrastructure.

---

## Step 6: Analyze the Second Event

| Parameter | Observation |
|---|---|
| **Event Time** | September 25, 2026, 16:56:54 (UTC+05:30) |
| **User Name** | - |
| **Event Name** | AutomatedDefaultVpcCreation |
| **Event Source** | ec2.amazonaws.com |
| **AWS Region** | eu-north-1 |
| **Read-only** | true |
| **Error Code** | - |
| **Activity** | Automated Default VPC creation |

---

# PART D - COMPARE THE EVENTS

## Step 7: Prepare the Audit Comparison

The two CloudTrail events were compared as follows:

| Parameter | Event 1 | Event 2 |
|---|---|---|
| **Event Time** | September 25, 2026, 16:56:54 | September 25, 2026, 16:56:54 |
| **User Name** | root | - |
| **Event Name** | CreateBucket | AutomatedDefaultVpcCreation |
| **Event Source** | s3.amazonaws.com | ec2.amazonaws.com |
| **AWS Region** | eu-north-1 | eu-north-1 |
| **Read-only** | false | true |
| **Error Code** | - | - |
| **Activity** | S3 bucket creation | Automated Default VPC creation |

---

# PART E - SECURITY AUDIT ANALYSIS

## Step 8: Identify Who, What, When and Where

### Event 1 — CreateBucket

| Question | Answer |
|---|---|
| **WHO?** | root |
| **WHAT?** | CreateBucket — S3 bucket creation |
| **WHEN?** | September 25, 2026, 16:56:54 |
| **WHERE?** | eu-north-1 |
| **RESULT?** | Successful — No error code |

### Event 2 — AutomatedDefaultVpcCreation

| Question | Answer |
|---|---|
| **WHO?** | - (AWS automated service activity) |
| **WHAT?** | AutomatedDefaultVpcCreation — Automated Default VPC creation |
| **WHEN?** | September 25, 2026, 16:56:54 |
| **WHERE?** | eu-north-1 |
| **RESULT?** | Successful — No error code |

---

# Step 9: Final Audit Table

| Parameter | Event 1 | Event 2 |
|---|---|---|
| **Event Time** | September 25, 2026, 16:56:54 | September 25, 2026, 16:56:54 |
| **User** | root | - |
| **Event Name** | CreateBucket | AutomatedDefaultVpcCreation |
| **Service** | Amazon S3 | Amazon EC2 |
| **Region** | eu-north-1 | eu-north-1 |
| **Read-only** | false | true |
| **Result** | Successful | Successful |
| **Activity** | S3 bucket creation | Automated Default VPC creation |

---

# RESULT

The cloud activities in AWS were successfully audited using **AWS CloudTrail Event History**. Two different AWS events, **CreateBucket** and **AutomatedDefaultVpcCreation**, were examined and compared based on event time, user identity, event name, event source, AWS Region, read-only status, and error status.

The experiment demonstrated how **AWS CloudTrail provides an audit trail for monitoring, accountability, security auditing, and investigation of cloud activities**.
