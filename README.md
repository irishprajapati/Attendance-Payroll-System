Company Payroll & Attendance Management System
A modular, configurable, and legally compliant system for managing employee attendance, leave, and payroll—designed for Nepali organizations and aligned with the Nepal Labor Act and the fiscal year 2081/2082 tax regulations.

Overview
This application provides an integrated solution for three core HR functions:

Attendance Management – Enforces daily check-in/check-out policies, tracks presence, and automates status assignment.
Leave Administration – Handles accrual, approval, and statutory compliance for multiple leave types.
Payroll Processing – Computes gross and net salary with support for allowances, overtime, bonuses, and Nepal-compliant tax and social security deductions.
The system is built for configurability, auditability, and regulatory alignment—making it suitable for SMEs and growing enterprises in Nepal.

Core Modules
Attendance Module
Employee Actions

Employees must check in and check out once per day.
Shift start times are configurable per department.
A 15-minute grace period is applied after the scheduled start time.
Auto-checkout occurs at the end of the shift if the employee does not manually check out.
Employees may view their own attendance records but cannot edit them.
Personal details such as email, phone, and location are editable; attendance logs are not.
Attendance Status Types

Present
Half Day (0.5 credit)
On Leave (Paid)
Unpaid Leave
Holiday
Weekend
Absent
Half-Day Logic

Standard workday: 8 hours.
Worked ≥4 and <8 hours → Half Day.
Worked <4 hours → Absent (1 full-day deduction).
HR Actions

View all employee check-in/check-out logs.
Manually correct attendance entries with mandatory remarks (audit trail preserved).
Resolve attendance disputes (must be filed within 2 calendar days).
Approve overtime hours and verify entries.
All manual modifications trigger a notification to the Super Admin.
System Rules

Absent status is auto-assigned if no check-in occurs by end of day.
Late arrivals beyond the grace period accumulate; every 3 hours late results in a 0.5-day deduction.
Overtime requires explicit HR or Admin approval.
Work-from-home (WFH) is configurable per company policy, including optional internet stipends.
Travel allowance is applied only for office attendance.
Offsite employees are marked “Present” for payroll but are not eligible for overtime unless explicitly approved.
Overtime Calculation

Weekday OT rate: 1.5 × hourly rate
Weekend/Holiday OT rate: 2.0 × hourly rate
Hourly rate = base_salary / (working_days_per_month × 8)
Overtime pay = total_ot_hours × hourly_rate × multiplier
Payroll & Salary Module
Salary Components

Base Salary: Fixed contractual amount (typically 60–70% of gross).
Allowances: Configurable (e.g., transport, meal, internet).
Bonuses: Performance-based or festival-related (e.g., Dashain/Tihar).
Deductions: Income tax, Provident Fund (PF) or Social Security Fund (SSF), insurance, CIT (if opted), and attendance penalties.
Taxation (Nepal FY 2081/2082)

Annual Income (NPR)
Tax Rate
Up to 500,000
1% (Social Security Tax only)
500,001 – 700,000
10%
700,001 – 2,000,000
20%
Above 2,000,000
30% (may increase to 36% with surcharge)
Additional Rules

Female employees receive a 10% rebate on total income tax.
PF and SSF are mutually exclusive:
PF: 10% employee + 10% employer
SSF: 11% employee + 20% employer (per SSF Act)
CIT contribution is optional and employee-initiated.
Unpaid leave results in daily salary deduction:
per_day_salary = gross_salary / total_working_days_in_month
Final Salary Formula

12345
Net Salary = Base Salary 
             + Allowances 
             + Overtime Pay 
             + Bonuses 
             - (Income Tax + PF/SSF + Other Deductions)
Leave Module
Leave Types and Policies

Type
Annual Entitlement
Paid
Carry Forward
Notes
Annual Leave
18 days
Yes
Yes (max 30)
Accrues at 1.5 days/month after 1 year of service
Sick Leave
12 days
Yes
No
Medical certificate required for >3 consecutive days
Casual Leave
6 days
Yes
No
For short-term emergencies only
Maternity Leave
98 days
Yes
N/A
Fully paid per Nepal Labor Act
Paternity Leave
5–15 days
Yes
Per policy
Defined by company
Unpaid Leave
Unlimited
No
N/A
Requires HR approval
Carry Forward Rules

Annual leave may be carried forward for up to 2 years.
Sick and casual leave expire at year-end.
Upon termination or resignation, unused annual leave is paid out.
Holiday Management

Admin defines weekly working days (5-day or 6-day week).
Public holidays can be added manually or synced via API.
Optional integrations: HamroPatro API or Google Calendar API.
Support for region- and religion-specific holidays.
System Configuration
Super Admins may configure:

Department-specific shift timings
Weekly working days and grace period (default: 15 minutes)
Overtime eligibility and approval workflow
WFH and offsite work policies
Payroll templates (PF vs SSF selection)
Holiday sources (manual entry or API-based sync)
Permissions Model
Employees:
Read-only access to their attendance and payroll data.
May update non-attendance profile fields (e.g., contact info).
HR Personnel:
Full read access to all employee records.
Authorized to correct attendance with audit logging.
Approve leave, overtime, and resolve disputes.
Super Admin:
Receives alerts on all manual attendance modifications.
Manages global system settings and policy templates.
Compliance and Design Principles
Fully aligned with the Nepal Labor Act and Inland Revenue Department guidelines for FY 2081/2082.
Business logic for tax, leave, and attendance is modular and isolated for reusability.
Attendance data directly feeds into payroll calculations—ensuring accuracy and traceability.
Designed with future analytics in mind (e.g., absence rates, overtime costs, leave utilization trends).
Suggested Tech Stack
Backend: Python, Django / Django REST Framework
Database: PostgreSQL (with timezone and JSONB support for dynamic configurations)
Authentication: JWT or session-based, with role-based access control
Deployment: Docker, Gunicorn, Nginx
APIs: RESTful interface with comprehensive documentation
Testing: Unit and integration tests for core payroll and attendance logic
This system prioritizes correctness, configurability, and regulatory compliance—enabling organizations to automate HR operations while maintaining legal adherence and operational transparency.

