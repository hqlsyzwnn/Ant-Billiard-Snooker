## Ant Billiard Snooker Management System

------------------------------------------------------------------------

# 1. Introduction

## 1.1 Purpose

The purpose of this Software Requirements Specification (SRS) is to
describe the functional and non-functional requirements of the Ant
Billiard Snooker Management System. This document provides a common
reference for the project stakeholders, developers, admins and employees
regarding the system's expected functions, limitations and operating
environment.

The system is intended to provide an online platform for managing
snooker table bookings and related activities across Ant Billiard
branches. Customers can create accounts, view table availability, make
booking requests, complete online payments and participate in points,
rewards and tournament activities.

Admins and employees use the system to manage customers, bookings,
tables and tournament activities. Admins also manage employee accounts,
rewards, announcements and administrative reports. Employees handle
daily operational activities such as updating table availability,
preparing tables, approving bookings, checking in arriving customers and
recording player results.

## 1.2 Scope

The Ant Billiard Snooker Management System is a responsive website for
one snooker business that operates multiple branches.

The system covers:

-   Customer account registration and login.
-   Login access for customers, admins and employees.
-   Viewing table availability by customers after login.
-   Booking requests based on a selected date and time.
-   Online payment for table bookings.
-   Employee review and approval of booking requests.
-   Booking rescheduling; customer cancellation is not supported.
-   Table status management.
-   Employee customer check-in when a customer arrives at the centre.
-   Separate daily check-in rewards for customers.
-   Player points and a leaderboard based on the number of wins.
-   Vouchers, reward levels and monthly champion rewards.
-   Tournament creation by admins, registration, registration fees,
    double-elimination brackets and match-result management.
-   Notifications through WhatsApp and email.
-   Admin sales reports, booking statistics and system reports.
-   Employee activity logging.

The system will be hosted online and will use Laravel, JavaScript and
PostgreSQL. Integration with a payment gateway, email service and
WhatsApp service is required.

The source requirements do not specify the exact payment provider,
notification providers, point values, voucher rules, report formats or
detailed branch-selection workflow. These details remain to be
confirmed.

## 1.3 Definitions, Acronyms and Abbreviations

  -----------------------------------------------------------------------
  Term                                Definition
  ----------------------------------- -----------------------------------
  SRS                                 Software Requirements Specification

  Admin                               User with full access to system
                                      administration functions

  Employee                            Staff member who manages daily
                                      snooker-centre operations

  Customer                            Snooker player who registers and
                                      uses the system

  Branch                              A physical Ant Billiard centre
                                      location

  Booking                             A customer's request to reserve a
                                      snooker table for a selected date
                                      and time

  Table status                        The current operational or
                                      reservation state of a snooker
                                      table

  Daily check-in                      Customer activity that earns daily
                                      points

  Employee check-in                   The operational process of
                                      recording a customer's arrival at
                                      the centre

  Leaderboard                         Ranking of players based on the
                                      total number of wins

  Voucher                             A reward that can be redeemed using
                                      points or issued by an admin

  Double elimination                  Tournament format in which a
                                      participant is eliminated after two
                                      losses

  TBC                                 To Be Confirmed
  -----------------------------------------------------------------------

# 2. Overall Description

## 2.1 Product Perspective

The Ant Billiard Snooker Management System is a new web-based management
platform for Ant Billiard. The business currently does not have a
website for online table bookings or a digital customer reward system.

The system is intended to support a single snooker business with
multiple branches. It will provide a shared online platform for
customers and staff to access the relevant booking and management
functions.

The system is not described as a replacement for an existing software
system. It introduces online booking and management capabilities while
employees continue to handle operational tasks such as table preparation
and booking approval.

The system will depend on external services for online payment, email
notifications and WhatsApp notifications.

## 2.2 Product Functions

The main functions of the system are summarized below.

  -----------------------------------------------------------------------
  Module                              Main functions
  ----------------------------------- -----------------------------------
  Customer management                 Customer registration, login and
                                      customer information management

  Admin management                    Full system access, employee
                                      registration, tournament creation,
                                      voucher management, announcements
                                      and reports

  Employee management                 Booking review and approval, table
                                      availability updates, customer
                                      check-in, customer and tournament
                                      management, player-point entry

  Table management                    Display and update table
                                      availability and status

  Booking management                  Select date and time, submit
                                      booking request, payment and
                                      rescheduling

  Payment                             Process online payments for table
                                      bookings and tournament
                                      registration fees

  Gamification                        Points for bookings, daily
                                      check-ins, tournaments and tasks

  Leaderboard                         Rank players based on total wins
                                      recorded by employees

  Rewards                             Point redemption, admin-issued
                                      vouchers, booking discounts and
                                      reward levels

  Tournament management               Admin-created tournaments,
                                      registration fees,
                                      double-elimination format,
                                      automatic bracket generation and
                                      result management

  Notification                        Booking confirmation, booking
                                      reminder, voucher reward, daily
                                      check-in reward and tournament
                                      announcement through WhatsApp and
                                      email

  Reporting                           Booking sales reports, booking
                                      statistics, system reports and
                                      employee activity logs
  -----------------------------------------------------------------------

## 2.3 User Classes and Characteristics

The system has three main user classes.

### 2.3.1 Customer

Customers are snooker players in areas near Ant Billiard branches.

Expected characteristics and access:

-   Must create their own account.
-   Must log in to access table availability and customer functions.
-   Can make booking requests and online payments.
-   Can request rescheduling but cannot cancel a booking.
-   Can participate in daily check-in, tournaments and tasks to earn
    points.
-   Can view rankings and use eligible vouchers.

### 2.3.2 Admin

Admins are responsible for managing the system and business information.

Expected characteristics and access:

-   Must log in.
-   Have full access to system functions.
-   Can register employee accounts.
-   Can create tournaments.
-   Can manage vouchers and rewards.
-   Can send announcements to customers.
-   Can view sales reports, booking statistics and other relevant system
    reports.
-   Can review employee activity logs.

### 2.3.3 Employee

Employees handle daily operations at the snooker centre.

Expected characteristics and access:

-   Must log in.
-   Can update table availability and table status manually.
-   Can review and approve booking requests.
-   Must ensure tables are ready before customers arrive for bookings.
-   Can manage customer information, bookings and tournament activities.
-   Can record customer arrival through employee check-in.
-   Can enter player IDs and points based on match results.
-   Employee accounts are registered by admins.

## 2.4 Operating Environment

The system is expected to operate in the following environment:

  -----------------------------------------------------------------------
  Item                                Requirement
  ----------------------------------- -----------------------------------
  Application platform                Web-based application

  User access                         Web browser

  Interface                           Responsive website

  Backend framework                   Laravel

  Frontend scripting                  JavaScript

  Database management system          PostgreSQL

  Hosting                             Online hosting

  External services                   Payment gateway, email service and
                                      WhatsApp service
  -----------------------------------------------------------------------

The exact supported browsers, minimum device specifications, server
specifications and hosting provider have not been specified.

## 2.5 Design and Implementation Constraints

The following constraints are stated or implied by the supplied project
requirements:

1.  The system must be developed as a responsive website.
2.  The selected backend framework is Laravel.
3.  JavaScript will be used for frontend scripting.
4.  PostgreSQL will be used as the database.
5.  The system must support one Ant Billiard business with multiple
    branches.
6.  Customers must log in before viewing table availability.
7.  Booking requests require employee approval.
8.  Customers cannot cancel bookings; they can only request
    rescheduling.
9.  Only admins can create tournaments.
10. Employee accounts can only be registered by admins.
11. The tournament format specified in the requirements is double
    elimination.
12. The system requires external payment, email and WhatsApp
    integrations.
13. The system will be hosted online.

No additional restrictions from a lecturer or project guideline were
identified in the supplied answers.

## 2.6 Assumptions and Dependencies

### 2.6.1 Assumptions

The following assumptions are used to organize the requirements. They
should be confirmed with the stakeholders:

-   Each Ant Billiard branch has its own set of snooker tables.
-   Table availability and booking records need to be associated with
    the relevant branch.
-   Customers have access to an internet connection and a web browser.
-   Admins and employees are provided with login accounts.
-   Employees are responsible for entering player IDs and match points.
-   The leaderboard can only be accurate when match results are entered
    correctly.
-   Customers can only use vouchers that meet the applicable redemption
    conditions.
-   A booking is not treated as approved until an employee approves it.

### 2.6.2 Dependencies

The system depends on:

-   An online hosting environment.
-   A working PostgreSQL database.
-   A payment gateway for online booking payments and tournament
    registration fees.
-   An email service for sending notifications.
-   A WhatsApp service for sending notifications.
-   Internet connectivity for customers and staff to access the hosted
    website.

The payment gateway and notification service providers have not yet been
selected.

# 3. Specific Requirements

## 3.1 Functional Requirements

Functional requirements describe the services and operations that the
system must provide.

### 3.1.1 Account and Access Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-001                  The system shall allow  Customer
                          customers to register   
                          their own accounts.     

  FR-002                  The system shall        All users
                          provide login access    
                          for customers, admins   
                          and employees.          

  FR-003                  The system shall        All users
                          restrict system         
                          functions according to  
                          the user's role.        

  FR-004                  The system shall allow  Admin
                          admins to register      
                          employee accounts.      

  FR-005                  The system shall allow  Admin, Employee
                          admins and employees to 
                          manage customer         
                          information according   
                          to their access         
                          permissions.            

  FR-006                  The system shall        Admin
                          provide admins with     
                          full access to system   
                          functions.              
  -----------------------------------------------------------------------

### 3.1.2 Branch and Table Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-007                  The system shall        Admin
                          support multiple        
                          branches under one Ant  
                          Billiard business.      

  FR-008                  The system shall allow  Employee
                          employees to update     
                          table availability.     

  FR-009                  The system shall allow  Employee
                          employees to manually   
                          update table status.    

  FR-010                  The system shall        System
                          maintain the table      
                          statuses Available,     
                          Occupied, Reserved and  
                          Maintenance.            

  FR-011                  The system shall allow  Customer
                          customers to view       
                          available tables after  
                          logging in.             
  -----------------------------------------------------------------------

### 3.1.3 Booking Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-012                  The system shall allow  Customer
                          customers to select a   
                          booking date and time.  

  FR-013                  The system shall allow  Customer
                          customers to submit a   
                          table booking request.  

  FR-014                  The system shall        Employee
                          require employee        
                          approval before a       
                          booking is confirmed.   

  FR-015                  The system shall allow  Employee
                          employees to view and   
                          manage booking          
                          requests.               

  FR-016                  The system shall allow  Customer
                          customers to request    
                          booking rescheduling.   

  FR-017                  The system shall not    System
                          provide customers with  
                          a booking cancellation  
                          function.               

  FR-018                  The system shall allow  Employee
                          employees to check in   
                          customers when they     
                          arrive at the centre.   

  FR-019                  The system shall allow  Employee
                          employees to ensure the 
                          reserved table is ready 
                          before the customer     
                          arrives.                
  -----------------------------------------------------------------------

### 3.1.4 Payment Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-020                  The system shall        System
                          integrate with an       
                          online payment gateway. 

  FR-021                  The system shall allow  Customer
                          customers to make       
                          online payments for     
                          table bookings.         

  FR-022                  The system shall        System
                          calculate the table     
                          booking charge based on 
                          the hourly table price. 

  FR-023                  The system shall treat  System
                          the booking payment as  
                          a deposit that is       
                          deducted during the     
                          one-hour playing        
                          session, according to   
                          the supplied            
                          requirement.            

  FR-024                  The system shall        Customer
                          support registration    
                          fee payments for        
                          tournaments.            
  -----------------------------------------------------------------------

**Payment clarification required:** The source states that customers pay
the price of one hour when booking and that the deposit is deducted
during the one-hour playing session. The exact meaning of this
deduction, payment timing, refund rules and handling of unused deposits
must be confirmed.

### 3.1.5 Gamification and Player Ranking

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-025                  The system shall award  System
                          points for customer     
                          bookings.               

  FR-026                  The system shall award  System
                          points for daily        
                          customer check-ins.     

  FR-027                  The system shall        System
                          support points for      
                          tournament activities.  

  FR-028                  The system shall        System
                          support points for      
                          completed tasks.        

  FR-029                  The system shall allow  Employee
                          employees to enter      
                          player IDs and points   
                          based on match results. 

  FR-030                  The system shall        System
                          generate a player       
                          leaderboard based on    
                          the total number of     
                          wins.                   

  FR-031                  The system shall        System
                          support daily check-in  
                          rewards.                

  FR-032                  The system shall        Admin
                          support monthly         
                          champion recognition    
                          and a prize             
                          arrangement.            

  FR-033                  The system shall allow  Customer
                          customers to view their 
                          points and ranking.     
  -----------------------------------------------------------------------

### 3.1.6 Voucher and Reward Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-034                  The system shall allow  Customer
                          customers to redeem     
                          points for vouchers.    

  FR-035                  The system shall allow  Admin
                          admins to issue         
                          vouchers to customers.  

  FR-036                  The system shall allow  Customer
                          eligible vouchers to be 
                          used for booking        
                          discounts.              

  FR-037                  The system shall        System
                          support reward levels   
                          such as Bronze, Silver  
                          and Gold.               

  FR-038                  The system shall allow  Customer
                          customers to view       
                          available vouchers and  
                          reward information.     
  -----------------------------------------------------------------------

### 3.1.7 Tournament Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-039                  The system shall allow  Admin
                          admins to create        
                          tournaments.            

  FR-040                  The system shall        System
                          support tournament      
                          registration fees.      

  FR-041                  The system shall        System
                          support the             
                          double-elimination      
                          tournament format.      

  FR-042                  The system shall        System
                          generate tournament     
                          brackets automatically. 

  FR-043                  The system shall allow  Admin, Employee
                          admins and employees to 
                          manage tournament       
                          activities.             

  FR-044                  The system shall allow  Admin, Employee
                          admins and employees to 
                          manage tournament       
                          results.                

  FR-045                  The system shall allow  Customer
                          customers to register   
                          for available           
                          tournaments.            
  -----------------------------------------------------------------------

### 3.1.8 Notification Management

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-046                  The system shall send   System
                          booking confirmation    
                          notifications.          

  FR-047                  The system shall send   System
                          booking reminder        
                          notifications.          

  FR-048                  The system shall send   System
                          voucher reward          
                          notifications.          

  FR-049                  The system shall send   System
                          daily check-in reward   
                          notifications.          

  FR-050                  The system shall send   System
                          tournament              
                          announcements.          

  FR-051                  The system shall        System
                          support WhatsApp and    
                          email notification      
                          channels.               

  FR-052                  The system shall allow  Admin
                          admins to send          
                          announcements to all    
                          customers.              
  -----------------------------------------------------------------------

### 3.1.9 Reports and Activity Logs

  -----------------------------------------------------------------------
  ID                      Requirement             User
  ----------------------- ----------------------- -----------------------
  FR-053                  The system shall        Admin
                          generate booking sales  
                          reports for admins.     

  FR-054                  The system shall        Admin
                          provide booking         
                          statistics for admins.  

  FR-055                  The system shall        Admin
                          provide relevant system 
                          reports for admins.     

  FR-056                  The system shall record System
                          employee activities.    

  FR-057                  The system shall allow  Admin
                          admins to review        
                          employee activity logs. 
  -----------------------------------------------------------------------

## 3.2 Non-Functional Requirements

The supplied question-and-answer document does not define measurable
performance, security, availability or usability targets. The following
requirements are limited to the quality characteristics supported by the
stated project direction. Quantitative targets must be agreed with
stakeholders.

  -----------------------------------------------------------------------
  ID                      Category                Requirement
  ----------------------- ----------------------- -----------------------
  NFR-001                 Usability               The system shall
                                                  provide a user
                                                  interface that
                                                  customers, admins and
                                                  employees can use to
                                                  access their respective
                                                  functions.

  NFR-002                 Responsiveness          The website shall use a
                                                  responsive design for
                                                  different screen sizes.

  NFR-003                 Compatibility           The system shall be
                                                  accessible through a
                                                  web browser. Specific
                                                  supported browsers are
                                                  TBC.

  NFR-004                 Access control          The system shall
                                                  restrict functions
                                                  according to customer,
                                                  admin and employee
                                                  roles.

  NFR-005                 Availability            The system shall be
                                                  hosted online so that
                                                  authorized users can
                                                  access it through the
                                                  internet. A formal
                                                  uptime target is TBC.

  NFR-006                 Data integrity          The system shall
                                                  maintain consistent
                                                  booking, table,
                                                  payment, customer and
                                                  player-result records.

  NFR-007                 Maintainability         The system shall be
                                                  developed using the
                                                  selected Laravel
                                                  framework, JavaScript
                                                  and PostgreSQL
                                                  technologies.

  NFR-008                 Integration reliability The system shall
                                                  communicate with the
                                                  selected payment, email
                                                  and WhatsApp service
                                                  providers.

  NFR-009                 Performance             Response-time and
                                                  concurrent-user targets
                                                  are TBC.

  NFR-010                 Security                Authentication,
                                                  authorization, secure
                                                  payment handling and
                                                  protection of customer
                                                  information shall be
                                                  addressed during
                                                  implementation.
                                                  Detailed security
                                                  standards are TBC.

  NFR-011                 Scalability             The system's data
                                                  structure shall
                                                  accommodate the
                                                  multiple branches
                                                  operated by Ant
                                                  Billiard.

  NFR-012                 Auditability            Employee activities
                                                  shall be recorded so
                                                  that admins can review
                                                  operational actions.
  -----------------------------------------------------------------------

## 3.3 External Interface Requirements

### 3.3.1 User Interface

The system shall provide a responsive web interface for three user
roles:

-   Customer interface for account registration, table availability,
    bookings, payments, points, vouchers and tournaments.
-   Admin interface for system administration, employee accounts,
    tournaments, vouchers, announcements and reports.
-   Employee interface for table availability, booking approval,
    customer check-in, customer management and tournament activities.

The exact page layouts, navigation structure, colours and accessibility
standards are not specified in the supplied requirements.

### 3.3.2 Hardware Interface

No special hardware interface is specified in the supplied requirements.
Users are expected to access the system using internet-connected devices
with a web browser.

Whether the system will connect to physical table sensors, payment
terminals, printers or other devices is TBC.

### 3.3.3 Software Interface

  -----------------------------------------------------------------------
  Interface                           Purpose
  ----------------------------------- -----------------------------------
  Laravel application                 Backend application framework

  JavaScript                          Frontend scripting

  PostgreSQL                          Store system data

  Payment gateway                     Process online booking and
                                      tournament registration payments

  Email service                       Deliver system notifications

  WhatsApp service                    Deliver system notifications and
                                      announcements
  -----------------------------------------------------------------------

The specific external service providers, APIs and integration protocols
are TBC.

### 3.3.4 Communication Interface

-   Customers, admins and employees access the system through the
    internet using a web browser.
-   The system sends notifications through email and WhatsApp.
-   The system communicates with the selected payment gateway to process
    online payments.

The exact communication protocols and provider configurations are TBC.

## 3.4 Database Requirements

### 3.4.1 Database Platform

The system shall use **PostgreSQL** as its database management system.

### 3.4.2 Data Requirements

Based on the functions described in the supplied requirements, the
database needs to store information related to:

  -----------------------------------------------------------------------
  Data area                           Information to store
  ----------------------------------- -----------------------------------
  User accounts                       Customer, admin and employee
                                      account information

  Branches                            Ant Billiard branch information

  Tables                              Table information and current
                                      status

  Bookings                            Customer booking requests, selected
                                      date and time, approval and
                                      rescheduling information

  Payments                            Booking and tournament payment
                                      records

  Customer check-ins                  Daily check-in records and
                                      employee-recorded arrival check-ins

  Player records                      Player identifiers and match
                                      results

  Points and rankings                 Points earned and player win
                                      records

  Rewards                             Reward levels, vouchers and
                                      redemption records

  Tournaments                         Tournament information,
                                      registration, fees, brackets and
                                      results

  Notifications                       Notification type, recipient and
                                      delivery information

  Tasks                               Tasks and related point awards

  Activity logs                       Employee actions for admin review
  -----------------------------------------------------------------------

### 3.4.3 Preliminary Data Relationships

The following relationships are proposed from the system functions and
are subject to confirmation:

-   A branch has multiple tables.
-   A branch can have multiple bookings.
-   A customer can make multiple bookings.
-   A table can be associated with multiple bookings over time.
-   A booking may have one or more related payment records, depending on
    the final payment design.
-   A customer can have multiple daily check-in records.
-   A customer can register for multiple tournaments.
-   A tournament can have multiple registrations and matches.
-   A player can have multiple match results and point records.
-   A customer can receive multiple vouchers and notifications.
-   An employee can perform multiple recorded activities.

### 3.4.4 Data Integrity

The database should maintain valid relationships between customers,
branches, tables, bookings, payments and tournament records. The exact
table definitions, primary keys, foreign keys, data types, validation
rules and retention periods must be designed during database design.

# 4. System Models

The models in this section are preliminary representations of the system
based on the supplied requirements. They are intended to help
stakeholders understand the proposed processes and data. They should be
reviewed and updated when the detailed workflow and database design are
confirmed.

## 4.1 Use Case Diagram

The use case diagram identifies the main interactions between the three
user roles and the system.

``` mermaid
flowchart LR
    Customer([Customer])
    Admin([Admin])
    Employee([Employee])
    Payment([Payment Gateway])
    Email([Email Service])
    WhatsApp([WhatsApp Service])

    subgraph System["Ant Billiard Snooker Management System"]
        UC1((Register and Login))
        UC2((View Table Availability))
        UC3((Make Booking))
        UC4((Make Online Payment))
        UC5((Request Rescheduling))
        UC6((View Points and Leaderboard))
        UC7((Daily Check-in))
        UC8((Redeem Voucher))
        UC9((Register Tournament))
        UC10((Manage Customer))
        UC11((Manage Employee Accounts))
        UC12((Manage Tables))
        UC13((Approve Booking))
        UC14((Employee Check-in))
        UC15((Enter Player Points))
        UC16((Create Tournament))
        UC17((Manage Tournament Results))
        UC18((Manage Vouchers and Rewards))
        UC19((Send Announcements))
        UC20((View Reports))
        UC21((Review Activity Logs))
        UC22((Send Notifications))
    end

    Customer --> UC1
    Customer --> UC2
    Customer --> UC3
    Customer --> UC4
    Customer --> UC5
    Customer --> UC6
    Customer --> UC7
    Customer --> UC8
    Customer --> UC9

    Admin --> UC1
    Admin --> UC10
    Admin --> UC11
    Admin --> UC12
    Admin --> UC16
    Admin --> UC17
    Admin --> UC18
    Admin --> UC19
    Admin --> UC20
    Admin --> UC21

    Employee --> UC1
    Employee --> UC10
    Employee --> UC12
    Employee --> UC13
    Employee --> UC14
    Employee --> UC15
    Employee --> UC17

    UC4 --> Payment
    UC22 --> Email
    UC22 --> WhatsApp
```

**Diagram notes:**

-   All three user roles must log in.
-   Customers register their own accounts.
-   Admins register employee accounts.
-   Only admins create tournaments.
-   Both admins and employees manage tournament activities and results.
-   Employees approve booking requests and record customer arrivals.
-   The payment gateway and notification providers are external systems.

## 4.2 Activity Diagram -- Customer Booking

This activity diagram illustrates the main booking process. The exact
sequence between payment and employee approval is not fully specified in
the supplied answers and must be confirmed.

``` mermaid
flowchart TD
    A([Start]) --> B[Customer logs in]
    B --> C[View available tables]
    C --> D[Select booking date and time]
    D --> E[Submit booking request]
    E --> F[Proceed with online payment]
    F --> G{Payment successful?}
    G -- No --> H[Display payment failure]
    H --> F
    G -- Yes --> I[Booking request awaits employee review]
    I --> J[Employee reviews booking]
    J --> K{Booking approved?}
    K -- No --> L[Booking is not approved]
    K -- Yes --> M[Booking is approved]
    M --> N[Send booking confirmation]
    N --> O[Employee prepares table]
    O --> P[Customer arrives]
    P --> Q[Employee records customer arrival]
    Q --> R[Update table status to Occupied]
    R --> S([End])
    L --> S
```

**Workflow clarification:** The diagram shows payment before employee
review as a provisional sequence. The source confirms both online
payment and employee approval but does not explicitly establish which
must happen first or what happens to a payment when a request is
rejected.

## 4.3 Activity Diagram -- Tournament Management

``` mermaid
flowchart TD
    A([Start]) --> B[Admin logs in]
    B --> C[Create tournament]
    C --> D[Set tournament details and registration fee]
    D --> E[Publish tournament]
    E --> F[Customer registers]
    F --> G[Customer pays registration fee]
    G --> H{Payment successful?}
    H -- No --> I[Registration payment unsuccessful]
    I --> G
    H -- Yes --> J[Record tournament registration]
    J --> K[Generate double-elimination bracket]
    K --> L[Admin or employee manages matches]
    L --> M[Record match results]
    M --> N[Update player wins and points]
    N --> O[Update leaderboard]
    O --> P([End])
```

The exact tournament registration rules, participant limits and match
scheduling rules are TBC.

## 4.4 Data Flow Diagram (DFD)

### 4.4.1 Context Diagram (Level 0)

The context diagram shows the system as one process and the main
external entities that exchange information with it.

``` mermaid
flowchart LR
    C[Customer]
    A[Admin]
    E[Employee]
    PG[Payment Gateway]
    NS[Email and WhatsApp Services]
    SYS((Ant Billiard Snooker Management System))

    C -->|Registration, login, booking, payment request, rescheduling, tournament registration| SYS
    SYS -->|Availability, booking status, points, rankings, vouchers, notifications| C

    A -->|User management, tournament details, rewards, announcements, report requests| SYS
    SYS -->|Reports, statistics, activity logs, system information| A

    E -->|Table updates, booking decisions, customer check-in, match results and points| SYS
    SYS -->|Booking information, table information, customer and tournament information| E

    SYS -->|Payment request| PG
    PG -->|Payment result| SYS

    SYS -->|Notification messages| NS
    NS -->|Delivery result, if supported by provider| SYS
```

### 4.4.2 DFD Level 1

The Level 1 DFD separates the system into its main processes and
conceptual data stores.

``` mermaid
flowchart TB
    C[Customer]
    A[Admin]
    E[Employee]
    PG[Payment Gateway]
    NS[Email and WhatsApp Services]

    P1((1.0 Account Management))
    P2((2.0 Booking and Table Management))
    P3((3.0 Payment Processing))
    P4((4.0 Points and Rewards))
    P5((5.0 Tournament Management))
    P6((6.0 Notification Management))
    P7((7.0 Reports and Activity Logs))

    D1[(D1 User Data)]
    D2[(D2 Branch and Table Data)]
    D3[(D3 Booking Data)]
    D4[(D4 Payment Data)]
    D5[(D5 Points and Voucher Data)]
    D6[(D6 Tournament Data)]
    D7[(D7 Notification Data)]
    D8[(D8 Activity Log Data)]

    C -->|Registration and login details| P1
    A -->|Employee account details| P1
    P1 <--> D1

    C -->|Booking and rescheduling requests| P2
    E -->|Approval, check-in and table updates| P2
    P2 <--> D2
    P2 <--> D3
    P2 -->|Payment details| P3

    C -->|Payment request| P3
    P3 -->|Payment request| PG
    PG -->|Payment result| P3
    P3 <--> D4
    P3 -->|Payment status| P2

    C -->|Daily check-in and voucher redemption| P4
    E -->|Player results and points| P4
    A -->|Voucher and reward management| P4
    P4 <--> D5

    A -->|Tournament creation| P5
    C -->|Tournament registration| P5
    E -->|Match results| P5
    P5 <--> D6
    P5 -->|Tournament points| P4

    P2 -->|Booking events| P6
    P4 -->|Reward events| P6
    P5 -->|Tournament announcements| P6
    A -->|Announcements| P6
    P6 <--> D7
    P6 -->|Messages| NS

    P1 -->|User activities| P7
    P2 -->|Booking and table activities| P7
    P4 -->|Points and reward activities| P7
    P5 -->|Tournament activities| P7
    P7 <--> D8
    A -->|Report request| P7
    P7 -->|Reports and activity logs| A
```

**DFD notes:**

-   Data stores are conceptual and do not represent finalized PostgreSQL
    tables.
-   The diagram groups related functions to make the main information
    flows understandable.
-   More detailed Level 2 DFDs can be created after the detailed
    processes are confirmed.

## 4.5 Entity Relationship Diagram (ERD)

The ERD below is a **preliminary conceptual ERD**. The supplied
requirements describe system functions but do not provide a finalized
database schema. Therefore, entity names and relationships below are
proposed to support those functions and require validation.

``` mermaid
erDiagram
    BRANCH ||--o{ SNOOKER_TABLE : contains
    BRANCH ||--o{ BOOKING : receives
    CUSTOMER ||--o{ BOOKING : makes
    SNOOKER_TABLE ||--o{ BOOKING : reserved_for
    BOOKING ||--o{ PAYMENT : has

    CUSTOMER ||--o{ DAILY_CHECKIN : records
    CUSTOMER ||--o{ POINT_TRANSACTION : earns
    CUSTOMER ||--o{ VOUCHER_REDEMPTION : redeems
    VOUCHER ||--o{ VOUCHER_REDEMPTION : used_in

    CUSTOMER ||--o{ TOURNAMENT_REGISTRATION : registers
    TOURNAMENT ||--o{ TOURNAMENT_REGISTRATION : has
    TOURNAMENT ||--o{ MATCH : contains
    MATCH ||--o{ MATCH_RESULT : records
    CUSTOMER ||--o{ MATCH_RESULT : participates_in
    EMPLOYEE ||--o{ MATCH_RESULT : records

    ADMIN ||--o{ TOURNAMENT : creates
    ADMIN ||--o{ EMPLOYEE : registers
    EMPLOYEE ||--o{ ACTIVITY_LOG : performs
    CUSTOMER ||--o{ NOTIFICATION : receives

    BRANCH {
        int branch_id PK
        string branch_name
        string address
    }

    SNOOKER_TABLE {
        int table_id PK
        int branch_id FK
        string table_status
        decimal hourly_rate
    }

    CUSTOMER {
        int customer_id PK
        string name
        string email
        string phone_number
        string password_hash
    }

    ADMIN {
        int admin_id PK
        string name
        string email
        string password_hash
    }

    EMPLOYEE {
        int employee_id PK
        int admin_id FK
        string name
        string email
        string password_hash
    }

    BOOKING {
        int booking_id PK
        int customer_id FK
        int branch_id FK
        int table_id FK
        datetime booking_start
        datetime booking_end
        string booking_status
    }

    PAYMENT {
        int payment_id PK
        int booking_id FK
        decimal amount
        string payment_status
        string payment_reference
    }

    DAILY_CHECKIN {
        int checkin_id PK
        int customer_id FK
        date checkin_date
        int points_awarded
    }

    POINT_TRANSACTION {
        int point_transaction_id PK
        int customer_id FK
        int points
        string activity_type
        datetime created_at
    }

    VOUCHER {
        int voucher_id PK
        string voucher_name
        string reward_level
        decimal discount_value
    }

    VOUCHER_REDEMPTION {
        int redemption_id PK
        int customer_id FK
        int voucher_id FK
        datetime redeemed_at
    }

    TOURNAMENT {
        int tournament_id PK
        int admin_id FK
        string tournament_name
        decimal registration_fee
        string format
    }

    TOURNAMENT_REGISTRATION {
        int registration_id PK
        int tournament_id FK
        int customer_id FK
        string registration_status
    }

    MATCH {
        int match_id PK
        int tournament_id FK
        string bracket_stage
        string match_status
    }

    MATCH_RESULT {
        int result_id PK
        int match_id FK
        int customer_id FK
        int employee_id FK
        int wins
        int points_awarded
    }

    NOTIFICATION {
        int notification_id PK
        int customer_id FK
        string notification_type
        string channel
        string delivery_status
    }

    ACTIVITY_LOG {
        int activity_log_id PK
        int employee_id FK
        string activity_description
        datetime activity_time
    }
```

### 4.5.1 ERD Clarifications

The conceptual ERD includes proposed entities based on the system
functions. The following items require confirmation:

1.  Whether admin and employee accounts should share one user-account
    table or use separate tables.
2.  Whether employee check-in and customer daily check-in should be
    stored separately. They represent different processes in the
    supplied requirements.
3.  Whether a booking can have multiple payment transactions.
4.  Whether tournament registration fees use the same payment structure
    as booking payments.
5.  How match winners, losses and player points should be stored.
6.  Whether tasks require separate task and task-completion entities.
7.  Whether vouchers are created individually for each customer or
    assigned from a shared voucher definition.
8.  Whether reward levels are calculated from points, wins or another
    condition.
9.  Whether a tournament match needs separate participant records for
    each player.
10. Whether branch-specific employee assignments are required.

# 5. Requirements Requiring Stakeholder Confirmation

The following matters are not fully specified in the supplied
question-and-answer document. They should be resolved before finalizing
the SRS and implementation.

  -----------------------------------------------------------------------
  No.                     Topic                   Clarification needed
  ----------------------- ----------------------- -----------------------
  1                       Branch selection        How customers select a
                                                  branch and whether they
                                                  can book tables at
                                                  different branches
                                                  using one account

  2                       Table availability      Whether availability is
                                                  calculated
                                                  automatically from
                                                  bookings or updated
                                                  manually by employees,
                                                  or both

  3                       Booking approval        Whether payment occurs
                                                  before or after
                                                  employee approval

  4                       Rejected booking        What happens to a
                                                  customer's payment if
                                                  an employee rejects a
                                                  booking

  5                       Deposit                 Exact meaning of the
                                                  one-hour deposit and
                                                  how it is deducted

  6                       Rescheduling            Rescheduling deadline,
                                                  number of allowed
                                                  changes and payment
                                                  adjustment rules

  7                       Daily check-in          Whether daily check-in
                                                  is restricted to one
                                                  reward per calendar day

  8                       Employee check-in       How employee arrival
                                                  check-in differs
                                                  operationally from
                                                  daily reward check-in

  9                       Points                  Exact points awarded
                                                  for bookings,
                                                  check-ins, tournaments
                                                  and tasks

  10                      Leaderboard             Ranking period and
                                                  tie-breaking rules

  11                      Monthly champion        How the monthly
                                                  champion is selected
                                                  and what prize is
                                                  awarded

  12                      Reward levels           Point thresholds and
                                                  benefits for Bronze,
                                                  Silver and Gold

  13                      Vouchers                Voucher expiry,
                                                  discount type, minimum
                                                  spend and usage limits

  14                      Tournaments             Registration limits,
                                                  tournament dates, match
                                                  rules and participant
                                                  eligibility

  15                      Tournament payment      Payment handling and
                                                  refund rules

  16                      Notifications           Selected WhatsApp and
                                                  email providers and
                                                  notification triggers

  17                      Reports                 Required report
                                                  formats, filters and
                                                  date ranges

  18                      Security                Password, session,
                                                  access-control and
                                                  data-protection
                                                  requirements

  19                      Performance             Expected number of
                                                  users and acceptable
                                                  response times

  20                      Hosting                 Hosting provider,
                                                  backup schedule and
                                                  availability target
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 6. Conclusion

The Ant Billiard Snooker Management System is intended to provide an
online platform for table booking and snooker-centre management across
multiple branches. It also introduces player points, leaderboards,
vouchers, rewards and tournament management to improve customer
engagement.

This SRS organizes the requirements gathered from the supplied
question-and-answer document into an initial specification. The
functional requirements, non-functional requirements, external
interfaces, database requirements and preliminary system models provide
a foundation for system design and development.

The items listed as To Be Confirmed should be discussed with the
stakeholders before the SRS is treated as the final approved
specification.
