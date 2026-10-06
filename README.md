# Auto Ticket Classification using Flow Designer

## Project Overview

**Auto Ticket Classification using Flow Designer** is a ServiceNow System Administrator project that automates the classification of IT support tickets.

The system analyzes the ticket's short description and automatically assigns the appropriate **Category** and **Subcategory** using ServiceNow Flow Designer.

## Problem Statement

School IT helpdesks receive multiple support requests such as Wi-Fi problems, projector failures, password issues, and slow computers.

Manually reviewing and categorizing every ticket requires additional effort and can result in inconsistent classification.

This project automates the classification process using ServiceNow Flow Designer.

## Objectives

* Automatically classify IT tickets when they are created.
* Reduce manual classification effort.
* Improve ticket routing efficiency.
* Maintain standardized ticket information.
* Send an email notification to the caller.
* Provide an easy-to-maintain no-code automation solution.

## Technologies Used

* ServiceNow
* ServiceNow System Administrator
* Flow Designer
* Custom Tables
* Choice Fields
* Reference Fields
* Dependent Choice Fields
* Email Notification
* Update Sets
* XML

## Main Components

### Custom Table

The project uses a custom table:

`Incident Workflow`

The table contains fields including:

* Number
* Caller
* Category
* Subcategory
* Short Description
* Description
* State
* Assigned Group
* Assigned to

## Category and Subcategory Mapping

| Category    | Subcategory     |
| ----------- | --------------- |
| Network     | Wi-Fi           |
| Hardware    | Projector       |
| Access      | Forgot Password |
| Performance | Slow Computer   |

## Flow Designer Automation

The flow is named:

`Auto Classify School IT Tickets`

The flow is triggered when a new Incident Workflow record is created.

### Classification Logic

| Keyword/Issue    | Category    | Subcategory     |
| ---------------- | ----------- | --------------- |
| WiFi / Network   | Network     | Wi-Fi           |
| Projector        | Hardware    | Projector       |
| Password / Login | Access      | Forgot Password |
| Slow / Hanging   | Performance | Slow Computer   |

After classification, an email notification is sent to the caller.

## Testing

### Test Case 1

**Input:**

`WiFi not working in library`

**Expected Result:**

* Category → Network
* Subcategory → Wi-Fi
* Email notification → Sent to caller

### Test Case 2

**Input:**

`Projector not turning on`

**Expected Result:**

* Category → Hardware
* Subcategory → Projector
* Email notification → Sent to caller

## ServiceNow Update Set

The project configuration has been exported as:

`Project_Update_Set.xml`

The XML file can be imported into another ServiceNow instance as an Update Set.

## Repository Structure

```text
Auto-Ticket-Classification-using-Flow-Designer/
│
├── README.md
│
├── ServiceNow/
│   └── Project_Update_Set.xml
│
├── Documentation/
│   └── Auto Ticket Classification using Flow Designer.pdf
│
└── Screenshots/
    ├── 01-update-set.png
    ├── 02-custom-table.png
    ├── 03-fields.png
    ├── 04-dependent-fields.png
    ├── 05-flow-designer.png
    ├── 06-testing.png
    └── 07-email-notification.png
```

## Project Purpose

This project demonstrates how ServiceNow Flow Designer can be used to create a no-code automation solution for IT ticket classification and notification.

## Future Enhancements

* Automatic assignment to support groups
* SLA tracking
* Additional ticket categories
* More keyword rules
* Predictive intelligence
* Advanced reporting and dashboards
