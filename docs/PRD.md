# Budget Buckets --- Product Requirements Document

**Version:** 3.0 --- Overarching Product & MVP PRD\
**Status:** Working product specification

## 1. Product Summary

**Budget Buckets** is a budgeting application that helps users
understand where their income is going, determine how much money is
genuinely safe to spend after obligations and financial commitments, and
intentionally manage that remainder using flexible spending buckets.

The core product flow is:

``` text
Income
  ↓
Expenses and recurring obligations
  ↓
Savings and debt commitments
  ↓
Safe flexible money
  ↓
Budget buckets
  ↓
Spending and reallocation
  ↓
End-of-period review
```

The bucket system is the product's distinctive feature, but Budget
Buckets does not assume that a new user already knows how much money is
safe to spend. The application first helps the user arrive at that
number.

------------------------------------------------------------------------

## 2. Problem

A bank-account balance does not tell a user how much money is truly
available.

Part of that balance may already be needed for:

-   Rent or mortgage
-   Transportation
-   Insurance
-   Utilities
-   Groceries
-   Subscriptions
-   Savings
-   Investments
-   Debt repayment
-   Other recurring obligations

Even after those obligations are accounted for, flexible money can
disappear through many small discretionary purchases without the user
understanding where it went.

Budget Buckets therefore addresses two connected questions:

1.  **Where is my income going?**
2.  **How much can I safely spend right now?**

------------------------------------------------------------------------

## 3. Core Product Principles

### 3.1 Calculate safe-to-spend money first

Flexible spending money is determined only after income, expenses,
savings commitments, and debt commitments have been accounted for.

``` text
Safe Flexible Money
=
Income
- Expenses
- Savings Commitments
- Debt Commitments
```

### 3.2 Budget around real paycheques

Budget Buckets should make uneven cash flow visible.

Two paycheques may contain the same income but have very different
flexible amounts because bills are not distributed evenly.

Example:

                               Paycheque 1   Paycheque 2
  -------------------------- ------------- -------------
  Income                           \$1,797       \$1,797
  Bills & essentials                 \$879       \$1,182
  Savings/debt commitments           \$350         \$150
  **Safe flexible money**        **\$568**     **\$465**

### 3.3 The total flexible budget is the hard boundary

Individual bucket allocations are flexible planning tools.

If priorities change, users should be able to move money between buckets
without changing the total safe flexible amount.

### 3.4 Reflect reality instead of punishing the user

Real spending must remain recordable even when it exceeds a bucket
allocation.

The application should warn and visually identify overspending, but
should not hide or block a legitimate transaction.

### 3.5 Keep the answer visible

The primary product question is:

> **How much can I safely spend right now?**

The active-period experience should make that answer immediately
available.

------------------------------------------------------------------------

## 4. Target User

Budget Buckets is intended for users who:

-   Receive income on a recurring schedule.
-   Want a holistic view of where their money is going.
-   Need to understand how obligations affect individual paycheques.
-   Want to distinguish committed money from safely spendable money.
-   Frequently lose track of discretionary spending.
-   Want more structure around flexible spending without making every
    bucket an inflexible limit.

------------------------------------------------------------------------

## 5. Product Scope Model

The product is organized into four layers.

### Layer 1 --- Money Coming In

-   Income
-   Pay schedule
-   Pay periods

### Layer 2 --- Money Already Spoken For

-   Essential expenses
-   Recurring bills
-   Subscriptions
-   Savings commitments
-   Investment commitments
-   Debt payments

### Layer 3 --- Safe-to-Spend Calculation

``` text
Income
- committed money
= safe flexible money
```

### Layer 4 --- Budget Buckets

The safe flexible amount is allocated among user-defined buckets such
as:

-   Eating Out / Takeout
-   Gifts / Niceties
-   Household / Personal
-   Charity / Giving
-   Convenience / Parking
-   Social / Entertainment
-   Buffer
-   Extra Debt / Savings
-   Other custom buckets

------------------------------------------------------------------------

# 6. MVP Experience

The frontend prototype demonstrated that the original multi-screen
concept can be consolidated into a smaller number of top-level screens
without removing the underlying budgeting workflow.

The target MVP uses **five primary screens plus modal/inline
interactions**.

------------------------------------------------------------------------

## 6.1 Dashboard

The Dashboard is the primary active-pay-period screen.

Its first responsibility is to answer:

> **How much can I safely spend right now?**

The Dashboard should display:

-   Safe flexible money
-   Total income
-   Total committed money
-   Flexible amount spent
-   Flexible amount remaining
-   Bucket balance/progress indicators
-   Recent transactions

The prototype uses four summary/stat tiles:

-   Income
-   Committed
-   Flexible Spent
-   Flexible Remaining

The user should be able to reach common actions without navigating
through a large hierarchy of screens.

------------------------------------------------------------------------

## 6.2 Income & Commitments

Income & Commitments combines functionality originally envisioned as
separate screens for:

-   Income management
-   Expense management
-   Savings/debt goals
-   Pay-period assignment
-   Pay-period overview

The screen presents financial information by paycheque.

Each paycheque can contain:

### Income

Examples:

-   Salary
-   Side income
-   One-time income

### Bills & Essentials

Examples:

-   Rent
-   Car payment
-   Insurance
-   Utilities
-   Groceries
-   Phone
-   Internet
-   Subscriptions
-   Other obligations

### Savings & Debt Commitments

Examples:

-   Credit-card payment
-   Emergency savings
-   TFSA/investment contribution
-   General savings
-   Loan repayment

Items should be editable, categorizable, and assignable between
paycheques.

The prototype also supports draggable line items as a convenient way to
reorganize paycheque assignments.

Each paycheque displays a running safe-flexible-money subtotal.

------------------------------------------------------------------------

## 6.3 Buckets

The Buckets screen combines:

-   Bucket allocation
-   Bucket selection/detail
-   Bucket transactions
-   Bucket progress
-   Reallocation

The screen displays:

### Overall bucket information

-   Total flexible money
-   Total allocated
-   Total unallocated

### Selected bucket information

-   Allocated amount
-   Amount spent
-   Amount remaining
-   Percentage used
-   Transactions assigned to the bucket

Users can:

-   Create buckets
-   Rename buckets
-   Change allocations
-   Delete unused buckets
-   Select a bucket
-   Review bucket transactions
-   Move money between buckets

A reallocation changes bucket allocations without changing the overall
flexible budget.

Example:

``` text
Gifts:  $60 → $75
Social: $40 → $25
```

------------------------------------------------------------------------

## 6.4 Review

The Review screen handles end-of-period review.

It summarizes:

-   Income received
-   Committed expenses
-   Savings/debt commitments
-   Starting flexible money
-   Flexible spending
-   Spending by bucket
-   Remaining flexible money

The user can classify the remaining amount as:

-   Carry forward
-   Savings
-   Debt
-   Buffer
-   Close without further allocation

For the MVP these are bookkeeping actions only. Budget Buckets does not
initiate real bank transfers.

Closing a pay period makes it read-only unless it is explicitly
reopened.

------------------------------------------------------------------------

## 6.5 Settings

Settings contains basic profile and application preferences.

The prototype includes:

-   Editable profile information
-   Pay-schedule preference
-   Notification preference

Some settings may initially be disabled until their corresponding
application functionality is implemented.

Settings is accessed through the profile/avatar control rather than
occupying a primary navigation position.

------------------------------------------------------------------------

# 7. Navigation

The prototype uses a persistent primary navigation containing:

-   Dashboard
-   Income & Commitments
-   Buckets
-   Review

Settings is accessed separately through the user's avatar/profile
control.

The MVP should preserve this compact navigation model unless usability
testing reveals a need to change it.

------------------------------------------------------------------------

# 8. Income Requirements

Users should ultimately be able to:

-   Add income
-   Edit income
-   Delete income
-   Categorize income
-   Mark income as recurring or one-time
-   Associate income with a pay period/paycheque

Irregular income should not automatically become recurring income.

------------------------------------------------------------------------

# 9. Expense & Commitment Requirements

Users should be able to:

-   Add expenses
-   Edit expenses
-   Delete expenses
-   Categorize expenses
-   Mark expenses as recurring or one-time
-   Assign obligations to the appropriate paycheque

Savings and debt commitments should be represented separately enough
that users can distinguish ordinary consumption from deliberate
financial goals.

For the initial implementation, paycheque assignment may be manual.

Automatic or intelligent bill-to-paycheque assignment is future scope.

------------------------------------------------------------------------

# 10. Safe Flexible Money

Safe flexible money is calculated per paycheque and across the active
pay period.

``` text
safe_flexible_money =
    total_income
    - total_expenses
    - total_savings_commitments
    - total_debt_commitments
```

The calculation must update whenever the user changes relevant income or
commitments.

The resulting amount becomes available for bucket allocation.

------------------------------------------------------------------------

# 11. Bucket Allocation

Users should be able to allocate safe flexible money among custom
buckets.

The interface should show:

``` text
Flexible:   $568
Allocated:  $500
Unallocated: $68
```

The application should warn when allocations exceed available flexible
money.

Users should not be required to use predefined categories.

------------------------------------------------------------------------

# 12. Transactions

Users should be able to record flexible spending against buckets.

A transaction contains:

-   Amount
-   Bucket
-   Date
-   Optional description

Transactions should immediately update:

-   Bucket spent amount
-   Bucket remaining amount
-   Overall flexible amount spent
-   Overall flexible amount remaining

Users should be able to edit or delete recorded transactions.

------------------------------------------------------------------------

# 13. Overspending

Bucket overspending is allowed.

If:

``` text
Gift bucket remaining: $60
Transaction: $75
```

the application should identify the \$15 overage.

The user may:

-   Reallocate money from another bucket
-   Record the transaction while leaving the bucket over budget
-   Cancel the transaction

The interface should visually distinguish an overspent bucket rather
than blocking the transaction.

------------------------------------------------------------------------

# 14. Reallocation

Users can move allocated money between buckets.

A reallocation must not change the overall flexible amount.

The product should make this behavior easy because bucket allocations
are intended to adapt to changing priorities during the pay period.

------------------------------------------------------------------------

# 15. Responsive Experience

The application should support desktop and mobile layouts.

The current prototype establishes the following responsive behaviors:

-   Primary navigation pills wrap on narrow screens instead of requiring
    horizontal scrolling.
-   Dashboard summary tiles remain in a compact 2×2 arrangement on
    mobile where practical.
-   Bucket summary values reduce/wrap appropriately instead of
    overflowing.
-   On narrow screens, the bucket switcher may collapse to the currently
    selected bucket and expand on demand.
-   Users should not need to scroll through the entire bucket list
    before reaching the selected bucket's information.

Current prototype breakpoints include approximately:

-   900px
-   760px
-   640px

These are implementation guidance rather than permanent product
requirements and may be adjusted when the production React UI is built.

------------------------------------------------------------------------

# 16. Authentication & User Accounts

The frontend prototype currently operates as a single implicit user.

The production application should include:

-   Account registration
-   Login
-   Logout
-   Persistent user-owned data

Authentication is therefore **deferred from the visual prototype but
remains part of the intended application MVP/backend implementation**.

The prototype's current logout action is non-functional and should not
be considered final product behavior.

------------------------------------------------------------------------

# 17. Pay Schedule

The prototype currently assumes a biweekly schedule.

The broader product should support:

-   Weekly
-   Biweekly
-   Semi-monthly
-   Monthly

Pay-schedule selection may be introduced after the core biweekly
workflow is functional.

The data and application design should avoid unnecessarily preventing
later support for these schedules.

------------------------------------------------------------------------

# 18. Pay-Period History

The prototype currently supports one active period and does not expose
historical periods.

The broader product should support viewing completed pay periods so
users can understand changes in their spending over time.

A historical view should eventually show information such as:

  Period             Flexible Start   Spent   Remaining
  ---------------- ---------------- ------- -----------
  Aug 12--25                  \$568   \$327       \$241
  Jul 29--Aug 11              \$490   \$421        \$69

This feature may follow the first functional active-period
implementation.

------------------------------------------------------------------------

# 19. Copy Forward

Future pay periods should not require users to reconstruct recurring
financial information manually.

The intended product should eventually allow the next period to reuse:

-   Recurring income
-   Recurring expenses
-   Savings/debt commitments
-   Bucket structure

The user should review and adjust copied values before beginning the
next period.

This is deferred from the current prototype.

------------------------------------------------------------------------

# 20. End-of-Period Lifecycle

The intended lifecycle is:

``` text
Active Pay Period
      ↓
Track Spending
      ↓
Review
      ↓
Classify Remainder
      ↓
Close Period
      ↓
Historical Period
      ↓
Create / Prepare Next Period
```

The prototype currently implements the review/close concept but not the
complete historical and next-period lifecycle.

------------------------------------------------------------------------

# 21. MVP Screen Model

The production application should begin from the five-screen model
validated by the prototype:

1.  Dashboard
2.  Income & Commitments
3.  Buckets
4.  Review
5.  Settings

Additional workflows such as registration/login may exist outside the
authenticated main navigation.

Modals, drawers, inline editing, and contextual controls should be
preferred over creating unnecessary standalone screens.

------------------------------------------------------------------------

# 22. Current Prototype vs. Product Requirements

The current static frontend prototype is a **design validation
artifact**, not the complete product implementation.

### Demonstrated in the prototype

-   Five-screen information architecture
-   Dashboard safe-to-spend presentation
-   Income and commitments grouped by paycheque
-   Manual paycheque organization
-   Safe-flexible calculations
-   Bucket allocation
-   Bucket spending
-   Reallocation
-   Overspending visualization
-   End-of-period review
-   Responsive layout behavior

### Deferred from the prototype but retained in the product direction

-   Real authentication
-   Persistent backend/database
-   Multiple users
-   Configurable pay schedules
-   Historical pay periods
-   Copy-forward behavior
-   Full period lifecycle
-   Automatic/intelligent bill assignment

The production React application does not need to reproduce the
prototype implementation structure (`Budget Buckets.html`, `bb-data.js`,
`bb-screens.js`, and `bb-app.js`). Those files represent the design
prototype only.

------------------------------------------------------------------------

# 23. Out of Scope

The initial product does not require:

-   Bank account integrations
-   Automatic bank transaction imports
-   Automated bank transfers
-   Credit-score tracking
-   Investment portfolio tracking
-   Stock tracking
-   Tax calculations
-   AI financial advice
-   Receipt scanning
-   Automatic merchant categorization
-   Shared household budgeting
-   Complex financial forecasting
-   Currency conversion
-   Loan amortization tools

These may be considered separately in future versions.

------------------------------------------------------------------------

# 24. MVP Success Criteria

The functional MVP succeeds when a user can:

``` text
Create / access their budget
      ↓
Enter income
      ↓
Enter and organize obligations by paycheque
      ↓
Set savings/debt commitments
      ↓
See safe flexible money
      ↓
Allocate flexible money into buckets
      ↓
Record spending
      ↓
Reallocate money when priorities change
      ↓
Always see how much is safely available
      ↓
Review and close the pay period
```

The most important success criterion remains:

> **At any point in the active pay period, the user can clearly
> distinguish money that is already committed from money that is
> genuinely safe to spend.**

------------------------------------------------------------------------

# 25. Product Roadmap Boundary

The MVP should prioritize the complete safe-to-spend loop before adding
broader financial-management features.

A reasonable progression is:

``` text
Prototype-validated UI
      ↓
Functional React application
      ↓
FastAPI + PostgreSQL persistence
      ↓
Authentication / user ownership
      ↓
Complete active pay-period workflow
      ↓
Historical periods / copy forward
      ↓
Additional pay schedules
      ↓
Future product enhancements
```

The product should remain centered on the safe-to-spend and
bucket-management experience even as supporting budgeting functionality
expands.
