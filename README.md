# Fitness-Influencer-Coaching-Platform

1. User
========

Stores authentication and account-related information.

user_id (PK, UUID)
name
email (unique)
phone
password
role (enum: admin, trainer, client, etc.)
createdAt
updatedAt

2. Clients
===========

Stores client-specific details.
client_id (PK)
age
gender
height
weight

3. Trainers
============

Stores trainer-specific information.
trainer_id (PK)
specialization
experience_years
bio
rating

4. Plans
=========
Defines available fitness plans.
plan_id (PK)
trainer_id (FK)
plan_name
description
duration_weeks
price
includes_diet (boolean)
includes_workout (boolean)

5. Subscriptions
================
Tracks client subscriptions to plans.

subscription_id (PK)
client_id (FK)
plan_id (FK)
start_date
end_date
status

6. Payment
===========
Handles payment transactions.

payment_id (PK)
subscription_id (FK)
amount
payment_date
payment_method
payment_status

7. Session
===========
Manages training sessions.

session_id (PK)
trainer_id (FK)
client_id (FK)
session_type
scheduled_date
duration_minutes
status

8. CheckIn
==========
Tracks client fitness progress.

checkin_id (PK)
subscription_id (FK)
checkin_date
weight
body_fat_percentage
