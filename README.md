# Salon Appointment Scheduler

An interactive command-line booking system for a salon, built with Bash and PostgreSQL. Customers choose a service, enter their phone number, and book a time. New customers are registered automatically.

## Tech used

Bash · PostgreSQL · SQL

## Files

| File | Description |
|---|---|
| `salon.sh` | The interactive booking script |
| `salon.sql` | Database dump to rebuild the database |

## Database structure

| Table | Description |
|---|---|
| `services` | The services offered (cut, color, perm, style, trim) |
| `customers` | Customers, identified by a unique phone number |
| `appointments` | Bookings, linking a customer and a service to a time |

## Features

- Displays the list of services straight from the database
- Shows the menu again if an invalid service is chosen
- Recognises returning customers by phone number
- Registers new customers automatically
- Confirms each booking with the service, time and customer name

## Example

```
~~~~~ MY SALON ~~~~~

Welcome to My Salon, how can I help you?

1) cut
2) color
3) perm
4) style
5) trim
1

What's your phone number?
555-555-5555

I don't have a record for that phone number, what's your name?
Fabio

What time would you like your cut, Fabio?
10:30

I have put you down for a cut at 10:30, Fabio.
```

## How to run it

```bash
psql -U postgres < salon.sql
./salon.sh
```

## What I learned

- Writing interactive Bash scripts with `read` and functions
- Validating user input
- Looking up and inserting related records across tables
- Designing a small booking database with foreign keys
