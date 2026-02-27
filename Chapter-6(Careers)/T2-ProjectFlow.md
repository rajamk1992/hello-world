# Sponcenter - Event Management System

## Complete Flow


------------------------------------------------------------------------

# 1. Introduction

## 1.1 Problem Statement

Event management today involves manual coordination between hosts,
venues, and service providers. There is no unified platform to manage
booking, services, and payments in one place.

## 1.2 Solution Overview

Sponcenter is a web-based event management system that allows: - Users
to host events - Vendors to list venues and services - Customers to book
events and services - Admin to manage the complete platform

------------------------------------------------------------------------

# 2. Business Requirement Document (BRD)

## 2.1 Business Objectives

-   Centralized event booking platform
-   Vendor visibility and digital presence
-   Secure online payment system
-   Reduce manual coordination

## 2.2 Stakeholders

-   Admin
-   Event Host
-   Vendor
-   End User

## 2.3 High-Level Requirements

-   User Registration & Login
-   Event Creation & Management
-   Venue & Service Listing
-   Booking Workflow
-   Payment Integration
-   Admin Dashboard & Reports

------------------------------------------------------------------------

# 3. User Requirement Document (URD)

## 3.1 User Roles

### End User

-   Register / Login
-   Search events
-   Select venue
-   Select services
-   Make payment
-   View booking history

### Vendor

-   Add / Update services
-   Manage pricing
-   View bookings

### Admin

-   Approve vendors
-   Manage users
-   View reports
-   Monitor transactions

------------------------------------------------------------------------

# 4. Functional Specification Document (FSD)

## Booking Module Flow

1.  User selects event
2.  Select venue
3.  Select required services
4.  System calculates total cost
5.  Payment processed
6.  Booking confirmation generated

## Validations

-   Date availability check
-   Vendor availability check
-   Payment status verification

------------------------------------------------------------------------

# 5. Effort Estimation

  Module                Estimated Days
  --------------------- ----------------
  Authentication        5
  Event Management      10
  Vendor Module         12
  Booking System        15
  Payment Integration   6
  Admin Panel           8
  Testing               10

Total Estimated Effort: 66 -- 75 Days

------------------------------------------------------------------------

# 6. Sprint Planning (2 Weeks Each)

## Sprint 1

-   Project setup
-   Authentication module
-   Database schema

## Sprint 2

-   Event & Venue module
-   Service management

## Sprint 3

-   Booking workflow
-   Payment integration

## Sprint 4

-   Admin dashboard
-   Reports

## Sprint 5

-   Testing
-   Bug fixing
-   Deployment

------------------------------------------------------------------------

# 7. Jira Structure

## EPIC: Event Management

### Story: Create Event

-   Design event form UI
-   Create API
-   Save data to DB
-   Field validation

### Story: Booking System

-   Booking API
-   Payment gateway integration
-   Confirmation email

------------------------------------------------------------------------

# 8. Data Flow Diagram (DFD)

## Level 0 - Context Diagram

User → Sponcenter System → Vendor\
User → Payment Gateway\
Admin → System

## Level 1

User → Booking Module → Database\
Booking Module → Payment Gateway\
Payment Gateway → Booking Module\
Booking Module → Notification Service

------------------------------------------------------------------------

# 9. System Architecture

Frontend: React / Angular\
Backend: Node.js + Express\
Database: MySQL\
Cloud: AWS (EC2, RDS, S3)

Architecture Flow:

Frontend → Backend API → MySQL Database\
Backend → Payment Gateway API\
Backend → Cloud Storage

------------------------------------------------------------------------

# 10. MySQL Database Structure

## Users Table

-   id (PK)
-   name
-   email
-   password
-   role
-   created_at

## Events Table

-   id (PK)
-   title
-   description
-   host_id (FK)
-   date
-   location

## Vendors Table

-   id (PK)
-   name
-   service_type
-   price

## Bookings Table

-   id (PK)
-   user_id (FK)
-   event_id (FK)
-   vendor_id (FK)
-   total_amount
-   payment_status

------------------------------------------------------------------------

# 11. UI/UX Screens

## User Screens

-   Login / Register
-   Dashboard
-   Event listing
-   Event details
-   Booking page
-   Payment page
-   Confirmation page

## Vendor Screens

-   Vendor dashboard
-   Add service
-   Manage bookings

## Admin Screens

-   User management
-   Vendor approval
-   Reports dashboard

------------------------------------------------------------------------

# 12. SDLC Lifecycle Followed

1.  Requirement Gathering
2.  BRD & URD Documentation
3.  System Design
4.  Development (Sprint-based Agile)
5.  Testing (Unit, Integration, UAT)
6.  Deployment
7.  Maintenance & Support

------------------------------------------------------------------------

# 13. Conclusion

Sponcenter simplifies event hosting and booking by providing: -
Centralized management - Transparent pricing - Secure transactions -
Scalable cloud-based architecture

This project demonstrates end-to-end project management including: BRD,
FSD, Estimation, Sprint Planning, Architecture, Database Design, and
Deployment Strategy.

