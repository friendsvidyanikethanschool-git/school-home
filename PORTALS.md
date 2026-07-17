# Portal planning

Working notes for each system linked from the homepage. Fill in / update this as each portal gets built — it's meant to be a living reference, not a one-time spec.

For each portal, three questions matter:
- **What's inside** — the actual features/screens
- **Who can edit data** — who has accounts with write access inside that portal
- **Who can view it** — who should even see the card on the homepage (controls the `data-audience` tag on its card: `all`, `staff`, or `parent-student`)

| Portal | Status | Homepage audience | What's inside | Who can edit | Who can view |
|---|---|---|---|---|---|
| Payroll | 🟢 Live | Staff only | Salary slips, tax declarations, reimbursements | *(fill in)* | *(fill in)* |
| Inventory | 🟢 Live | Staff only | Stock levels, requests, issue records | *(fill in)* | *(fill in)* |
| School ERP | ⚪ Placeholder | Staff · Students | Admissions, attendance, timetables, exams, records | | |
| Digital Library | ⚪ Placeholder | Everyone | E-books, journals, past papers | | |
| Learning Portal | ⚪ Placeholder | Staff · Students | Assignments, study material, announcements | | |
| Parent Portal | ⚪ Placeholder | Parents · Students | Fee payments, report cards, teacher messages | | |
| Staff Webmail | ⚪ Placeholder | Staff only | Official email, circulars | | |

## Notes

- The homepage toggle (Everyone / I'm Staff / I'm Parent-Student) only controls what's **shown** on the homepage — it is not real access control. Actual login and permissions have to live inside each portal itself.
- When a placeholder goes live: open `index.html`, find the matching `<!-- TODO -->` comment, and replace the `javascript:void(0)` link with the real URL (same pattern already used for Payroll and Inventory).
- If a portal's audience changes, update its card's `data-audience="..."` attribute (`all`, `staff`, or `parent-student`).
