Courtroom Scheduling: Create a database to schedule courtrooms, judges, and hearings efficiently.
# Courtroom Scheduling Database

## Executive Summary

The Courtroom Scheduling Database aims to efficiently manage the scheduling of courtrooms, judges, and hearings. This MongoDB document database will provide a flexible and scalable solution to organize and track judicial proceedings effectively.

## Project Requirement

The primary objective of this project is to design a MongoDB document database capable of:
- Scheduling hearings in specific courtrooms at designated times.
- Assigning judges to hearings based on availability and expertise.
- Tracking relevant information for each hearing, including case details, parties involved, and scheduled duration.
- Supporting updates, cancellations, and rescheduling of hearings as needed.
- Providing a user-friendly interface for accessing and managing scheduling data.

## Data Model

### 1. Courtrooms Collection
- **_id**: Unique identifier for each courtroom.
- **name**: Name or identifier for the courtroom.
- **location**: Location of the courtroom (e.g., courthouse address).
- **capacity**: Maximum seating capacity of the courtroom.
- **availability**: Array of objects representing available time slots for hearings.

### 2. Judges Collection
- **_id**: Unique identifier for each judge.
- **name**: Name of the judge.
- **specialization**: Area of expertise or type of cases the judge handles.
- **availability**: Array of objects representing available time slots for hearings.

### 3. Hearings Collection
- **_id**: Unique identifier for each hearing.
- **case_number**: Identifier for the legal case associated with the hearing.
- **courtroom_id**: Reference to the courtroom where the hearing will take place.
- **judge_id**: Reference to the judge presiding over the hearing.
- **start_time**: Scheduled start time for the hearing.
- **end_time**: Scheduled end time for the hearing.
- **parties**: Array of objects representing parties involved in the case.
- **status**: Current status of the hearing (e.g., scheduled, canceled, completed).
- **notes**: Additional notes or details about the hearing.

### 4. Users Collection
- **_id**: Unique identifier for each user.
- **username**: Username of the user accessing the system.
- **email**: Email address of the user.
- **password**: Encrypted password for user authentication.
- **role**: Role of the user within the system (e.g., admin, clerk, judge).

### 5. Logs Collection
- **_id**: Unique identifier for each log entry.
- **user_id**: Reference to the user who performed the action.
- **action**: Description of the action performed (e.g., scheduled hearing, updated judge availability).
- **timestamp**: Timestamp indicating when the action occurred.

