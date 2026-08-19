# 🏥 Hospital Appointment Management System (HAMS)
> **ServiceNow Scoped Application (`x_2065601_hospit_0`)**

An enterprise-grade ServiceNow portal application designed to digitalize clinical scheduling, manage doctor availability, automate waitlist promotions, and streamline daily outpatient operations.

---

## 📌 Executive Summary
The **Hospital Appointment Management System (HAMS)** replaces manual, paper-based, and fragmented scheduling systems with a unified ServiceNow Service Portal (`/hams`). Built on native ServiceNow scoped tables, HAMS eliminates double-booking through an **Atomic Booking Engine** and ensures optimal slot utilization using an **Event-Driven Waitlist Auto-Promotion System**.

---

## 👥 Targeted User Personas & Solved Pain Points

* **🏥 Patient:** Real-time visibility into specialist availability to book, manage, or cancel appointments online without endless phone calls.
* **👨‍⚕️ Doctor:** Capability to auto-generate daily availability slots, manage daily patient queues in real-time, and eliminate idle time caused by late cancellations.
* **📋 Front-Desk Admin:** Unified dashboard to manage walk-in registrations, monitor cross-doctor daily schedules, and handle administrative schedule overrides.

---

## 🛠️ Key Technical Features

* **Atomic Slot Booking Engine:** Prevents concurrent transaction race conditions by validating and locking availability slots in a single server-side transaction.
* **Event-Driven Waitlist Auto-Promotion:** Automatically promotes waiting patients into newly opened slots when an appointment is canceled or marked as a no-show.
* **Role-Based Access Control (ACLs):** Enforces data security at the table and field levels across Patient, Doctor, and Admin roles.
* **Service Portal Interface:** Built using AngularJS widgets (`hospital_booking`) organized into 7 operational tabs:
  1. `Home` - Central metrics and navigation portal
  2. `Patient Registration` - Self-service patient onboarding
  3. `Patient Booking & History` - Real-time slot search & appointment lifecycle management
  4. `Doctor Registration` - Profile, specialty, shift, and fee configurations
  5. `Doctor Queue & Slots` - Dynamic slot generator matrix & real-time daily queue
  6. `Front Desk / Admin` - Walk-in patient processing & schedule overrides
  7. `Waitlist` - Queue positioning and promotion logs

---

## 🗄️ Data Model Schema

The application relies on 5 core scoped tables inside `x_2065601_hospit_0`:

| Table Name | Internal Table Name | Description |
| :--- | :--- | :--- |
| **Patient** | `x_2065601_hospit_0_patient` | Stores patient demographics, medical history, and contact details |
| **Doctor** | `x_2065601_hospit_0_doctor` | Links to `sys_user` with shift, fee, and specialization data |
| **Availability Slot** | `x_2065601_hospit_0_doctor_availability_slot` | Tracks individual time slots (`Available`, `Booked`, `Cancelled`, `Blocked`) |
| **Appointment** | `x_2065601_hospit_0_appointment` | Manages appointment status (`Booked`, `Checked-In`, `Completed`, `Cancelled`, `No-Show`) |
| **Waitlist** | `x_2065601_hospit_0_waitlist` | Tracks waiting queue priorities (`Waiting`, `Promoted`, `Expired`, `Cancelled`) |

---

## 📂 Repository Directory Structure

```text
.
├── 1.IDEATION PHASE/           # Brainstorming, Problem Statements & Empathy Maps
├── 2.Project Planning Phase/    # Project Plan, Timelines & Architecture Diagrams
├── 3.Project Development Phase/ # Source Code, Business Rules & Testing Logs
├── 4.PROJECT DOCUMENTATION/     # Master Capstone Documentation PDF & Folder README
└── 5. PROJECT DEMONSTRATION/    # Video Walkthroughs, Screenshots & Demo Links
