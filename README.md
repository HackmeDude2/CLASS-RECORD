# CLASS-RECORD
full-stack academic attendance and institutional ledger management system developed using Python (Flask framework) and SQLite3 database. The project digitizes traditional paper-based college registers into a modern, role-secured web application supporting *Full 1-Year Academic Records (Jan to Dec)** with complete month-by-month and annual tracking.
# CLASS RECORDS — 1-Year Academic Presentation Slides (PPT)

> 🎤 **Presentation for Ma'am — 10 Slides (1-Year Academic Attendance Suite)**

---

````carousel
## 🏛️ Slide 1 — Title Slide

---

# CLASS RECORDS
### Full 1-Year Academic Attendance & Payroll Management Suite

---

| | |
|---|---|
| **Developed By** | Rudraksh Garg |
| **Company** | The ShivaGroups of App |
| **Technology** | Python • Flask • SQLite3 |
| **Scope** | Full 1-Year Academic Record (12 Months • Jan to Dec) |

---

*"Comprehensive annual student attendance tracking with multi-tier role security"*

<!-- slide -->

## 📋 Slide 2 — Introduction & 1-Year Need

---

### 🔴 The Need for 1-Year Records

Traditional single-month registers fail because:
- ❌ College semester rules mandate a **75% minimum across the entire academic year**
- ❌ Faculty holidays must be audited across all 12 months for payroll accuracy
- ❌ Students need cumulative visibility of attendance before final exams

---

### 🟢 Solution — CLASS RECORDS 1-Year Suite

A complete full-year digital ledger that:
- Maintains all **12 months of student and faculty records**
- Provides a **1-Year Master Annual Register** + **Monthly Detail View**
- Auto-calculates annual eligibility percentages in real-time

<!-- slide -->

## 🎯 Slide 3 — Core Features & 3-Portal Model

---

### 3 Segregated Secure Portals

```
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│ 🎓 TEACHER      │  │ ⚙️ ADMIN PANEL  │  │ 📚 STUDENT      │
│   PORTAL        │  │                 │  │   PORTAL        │
│                 │  │                 │  │                 │
│ Faculty PIN     │  │ 4-Digit PIN     │  │ Direct Name     │
│ (1111)          │  │ (1234)          │  │ Selection       │
│                 │  │                 │  │                 │
│ Mark P / A / L  │  │ Annual Payroll  │  │ Read-Only View  │
│ Any date of yr  │  │ Fee Ledger      │  │ Cumulative %    │
└─────────────────┘  └─────────────────┘  └─────────────────┘
```

- **Teacher:** Exclusive permission to mark attendance
- **Admin:** Exclusive access to salary deductions, fee collection, subject classes
- **Student:** View-only access with zero edit permissions

<!-- slide -->

## 🛠️ Slide 4 — Technology Stack

---

```
Backend Engine   →  Python 3.14 + Flask 3.0 REST API
Database         →  SQLite3 (Persistent ACID storage)
Frontend Layer   →  HTML5 + CSS3 + Vanilla JavaScript
Design Theme     →  Luxury Dark Obsidian & Champagne Gold
Test Suite       →  Python unittest (6 test cases, 100% passing)
Hosting          →  Flask WSGI Server on http://127.0.0.1:5050
```

---

### Why SQLite3 & Python?
- Zero external configuration required; runs out-of-the-box
- Fast relational joins linking students, teachers, sessions, and attendance

<!-- slide -->

## 📅 Slide 5 — 1-Year Master Register

---

### Comprehensive 12-Month Grid

The **1-Year Register** displays a bird's-eye view of every student:
- Columns for all 12 months: **Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec**
- Monthly class ratio (e.g. `16/18`) and % badge per month
- **Annual Cumulative Totals:**
  - Total Present, Total Absent, Total Approved Leaves
  - Cumulative Ratio (e.g., `156/180`)
  - Overall Annual Attendance Percentage
  - Outstanding Student Fee Balance

*One click toggles into the detailed 30-day daily calendar matrix!*

<!-- slide -->

## 📚 Slide 6 — Student Portal (Annual Progression)

---

### Complete Academic Visibility for Students

1. **🌟 1-Year Cumulative Attendance Card:**
   - Instant calculation: `156/180 classes (86.7%)`
   - Comparison against the institutional target (`≥ 75%`)
2. **📅 12-Month Academic Progression Table:**
   - Shows monthly presence, leaves, ratio, and "On Track" badge for every month of the year
3. **📚 Subject-Wise Annual Breakdown:**
   - Detailed attendance ratios across Python, DSA, Discrete Math, Digital Logic, and Labs

*Strictly read-only: Students cannot alter any records.*

<!-- slide -->

## 🧮 Slide 7 — Formulas & Calculation Logic

---

### 1. Attendance Percentage Formula
$$\text{Attendance \%} = \frac{\text{Present} + (\text{Leave} \times 0.5)}{\text{Total Classes Held}} \times 100$$
*(Approved leaves deduct less percentage than unexcused absences!)*

---

### 2. Teacher Holiday Deduction (>4 Rule)
$$\text{Deduction} = \max(0, \text{Holidays} - 4) \times \left(\frac{\text{Monthly Salary}}{\text{Days in Month}}\right)$$

*Example:* ₹54,000 salary, 6 holidays taken in November (30 days):
- Extra Holidays = $6 - 4 = 2\text{ days}$
- Per Day Rate = ₹$54,000 / 30 = \text{₹}1,800$
- Deduction = $2 \times \text{₹}1,800 = \text{₹}3,600$
- Net Monthly Payout = ₹$50,400$

<!-- slide -->

## 💰 Slide 8 — 12-Month Teacher Payroll Ledger

---

### Admin-Only Salary Control

- **Audit across all 12 months:** The system tracks teacher holidays taken in each month from January to December.
- **Automated Threshold:** Every month allows up to **4 free holidays**. Any excess immediately computes the exact salary deduction.
- **Annual Summary:** Displays total gross salary earned, total annual holiday deductions, and annual net payout.
- **Interactive Simulator:** Admin can simulate different holiday counts to verify deduction rates before running monthly payroll.

<!-- slide -->

## 🧪 Slide 9 — Quality Assurance & Testing

---

### Unit Test Suite Results (`python -m unittest`)

| Test Case | Verification Target | Status |
|---|---|---|
| `test_student_0_of_1_then_1_of_2` | Verifies dynamic 0/1 → 1/2 (50%) attendance | ✅ PASS |
| `test_leave_has_less_percentage_minus` | Validates 0.5× weight for approved leaves | ✅ PASS |
| `test_teacher_deduction_only_above_4` | Verifies 0 cut for ≤4 days; deduction on >4 | ✅ PASS |
| `test_student_fees_left_calculation` | Verifies fee dues, partial pay & overdue flags | ✅ PASS |
| `test_admin_only_subject_creation` | Verifies teachers/students cannot add subjects | ✅ PASS |
| `test_teacher_holiday_update_and_exports` | Verifies admin edits and CSV exports | ✅ PASS |

```
Ran 6 tests in 0.571s — OK (All Passed)
```

<!-- slide -->

## 🏁 Slide 10 — Conclusion

---

### Key Accomplishments

- 🎓 Transformed manual paper registers into a **Full 1-Year Academic Suite**
- 🔐 Three dedicated password-protected portals with strict RBAC enforcement
- 📊 Real-time dynamic attendance calculations across 12 months
- ⚖️ Fair attendance calculation honoring medical/approved leaves (0.5×)
- 💰 Automated 12-month teacher payroll deductions for holidays exceeding 4 days
- 🌟 Production-ready, luxury glassmorphic responsive UI

---

**Developed by:** RUDRAKSH GARG | **THE SHIVAGROUPS OF APP | CLASS RECORDS**
````
