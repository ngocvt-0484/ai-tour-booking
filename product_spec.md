# AI Tour Booking — Product Specification

## 1. Product Overview

AI Tour Booking is a small demo web application for booking tours.

The purpose of this project is not to build a production-ready booking platform.

The primary goal is to demonstrate an AI-driven software development workflow using:

- Ruby on Rails
- Claude Code
- Agent Skills
- Automated tests
- AI-assisted code review
- Harness engineering

The application allows customers to browse available tours and create bookings.

Admins can manage tours and view bookings.

---

## 2. Goals

### Primary Goals

1. Demonstrate AI-assisted product development.
2. Demonstrate Claude Code working with a Rails codebase.
3. Demonstrate AI-generated implementation from product requirements.
4. Demonstrate AI-generated tests.
5. Demonstrate AI-assisted code review.
6. Demonstrate agent skills.
7. Demonstrate automated verification and harness engineering.

### Non-Goals

This demo does not need:

- Real payment processing
- Real email delivery
- Complex authentication
- External tour provider integrations
- Mobile applications
- Microservices
- Advanced recommendation systems
- Production-grade scalability

---

# 3. User Roles

The application has two roles.

## Customer

A customer can:

- Browse tours
- View tour details
- Create a booking
- View their bookings

## Admin

An admin can:

- Create tours
- Edit tours
- Delete tours
- View bookings

---

# 4. Tour

A Tour contains:

| Field | Description |
|---|---|
| name | Tour name |
| description | Tour description |
| destination | Tour destination |
| price | Price per person |
| duration_days | Number of tour days |
| available_slots | Number of available seats |
| active | Whether the tour is available |

### Business Rules

1. Tour name is required.
2. Destination is required.
3. Price must be greater than 0.
4. Duration must be greater than 0.
5. Available slots cannot be negative.
6. Inactive tours cannot be booked.

---

# 5. Booking

A Booking contains:

| Field | Description |
|---|---|
| customer_name | Customer name |
| customer_email | Customer email |
| tour | Selected tour |
| booking_date | Date of the booking |
| number_of_people | Number of people |
| total_price | Total booking price |
| status | Booking status |

Possible statuses:

- pending
- confirmed
- cancelled

---

# 6. Booking Rules

When creating a booking:

1. The selected tour must exist.
2. The tour must be active.
3. Number of people must be greater than 0.
4. Number of people cannot exceed available slots.
5. Total price is:

```text
tour.price * number_of_people
```

6. Available slots are reduced after a successful booking.
7. Booking creation and slot reduction must happen atomically.
8. A failed booking must not reduce available slots.

---

# 7. Customer Features

## 7.1 Tour List

Customer can see:

- Tour name
- Destination
- Price
- Duration
- Available slots

Customer can filter tours by destination.

Only active tours should be displayed.

---

## 7.2 Tour Detail

Customer can see:

- Tour name
- Description
- Destination
- Price
- Duration
- Available slots

Customer can start the booking process.

---

## 7.3 Create Booking

Customer enters:

- Name
- Email
- Booking date
- Number of people

System validates the booking.

If successful:

- Booking is created.
- Total price is calculated.
- Available slots are reduced.
- Customer sees a confirmation page.

If unsuccessful:

- Booking is not created.
- Available slots remain unchanged.
- User sees validation/error information.

---

## 7.4 My Bookings

Customer can view their bookings.

Each booking shows:

- Tour
- Booking date
- Number of people
- Total price
- Status

---

# 8. Admin Features

Admin can:

## Tour Management

- List tours
- Create tour
- Edit tour
- Delete tour
- Activate/deactivate tour

## Booking Management

Admin can view all bookings.

Admin can see:

- Customer
- Tour
- Booking date
- Number of people
- Total price
- Status

---

# 9. Minimal Data Model

The application should initially contain:

```text
User
Tour
Booking
```

Suggested relationships:

```text
User
 └── has_many :bookings

Tour
 └── has_many :bookings

Booking
 ├── belongs_to :user
 └── belongs_to :tour
```

Authentication may initially be simplified for the demo.

---

# 10. Acceptance Criteria

## Tour

- [ ] Admin can create a tour.
- [ ] Admin can edit a tour.
- [ ] Admin can deactivate a tour.
- [ ] Customers cannot book inactive tours.
- [ ] Customers can browse active tours.
- [ ] Customers can filter tours by destination.

## Booking

- [ ] Customer can create a booking.
- [ ] Invalid booking is rejected.
- [ ] Booking total price is calculated correctly.
- [ ] Available slots decrease after successful booking.
- [ ] Available slots do not change after failed booking.
- [ ] Booking cannot exceed available slots.
- [ ] Booking creation is atomic.

## Testing

The application must contain automated tests for:

- Tour validations
- Booking validations
- Booking price calculation
- Slot reduction
- Failed booking behavior
- Inactive tour booking prevention

---

# 11. AI Development Requirements

The project should be developed using an AI-driven workflow.

Claude Code should be used for:

1. Understanding the specification
2. Creating implementation plans
3. Generating Rails code
4. Generating tests
5. Debugging
6. Refactoring
7. Code review
8. Security review
9. Documentation updates

The developer remains responsible for:

- Product decisions
- Architecture decisions
- Reviewing AI-generated code
- Approving changes
- Validating business behavior

---

# 12. AI Agent Requirements

The project should progressively introduce:

### Level 1

Claude Code as coding assistant.

### Level 2

Reusable Agent Skills for:

- Rails feature development
- Rails testing
- Code review
- Security review

### Level 3

Harness engineering:

- Automated tests
- Linting
- Security scanning
- Acceptance criteria verification
- Git diff verification
- CI checks

The objective is to allow an AI agent to determine whether its own implementation satisfies the defined requirements.

---

# 13. Definition of Done

A feature is considered complete when:

1. Product requirement is understood.
2. Implementation plan exists.
3. Code is implemented.
4. Automated tests are added.
5. Tests pass.
6. Linter passes.
7. Security scan passes.
8. Acceptance criteria are satisfied.
9. Git diff is reviewed.
10. Human developer approves the change.

---

# 14. Demo Success Criteria

The project is successful if a developer can demonstrate the following workflow:

```text
Product requirement
        ↓
Claude creates plan
        ↓
Claude implements feature
        ↓
Claude creates tests
        ↓
Tests execute
        ↓
Claude fixes failures
        ↓
Claude performs code review
        ↓
Security checks run
        ↓
Acceptance criteria verified
        ↓
Human approves
```

The quality of the AI development workflow is more important than the complexity of the booking application.