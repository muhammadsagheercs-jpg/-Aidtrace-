# AidTrace

**Making sure relief aid reaches the right family, once.**

AidTrace is a lightweight web demo for tracking disaster relief aid, such as after floods. When many families lose their homes and papers, aid is often given twice to some families and missed entirely for others. AidTrace gives every family a unique Household ID (for example `KHP-07-000001`) and records every step, from the first flood alert to the last distribution.

> This is a demo with sample data. It is not meant for real beneficiary data.

---

## The problem

- Families lose their papers, phones and homes in a disaster.
- The same family is registered more than once, or receives the same aid twice.
- Other families are missed completely.
- Nobody can easily see who changed what, or why.

## The solution

| Problem | How AidTrace helps |
|---|---|
| No papers | Registration works without a phone or ID card. The Household ID card replaces papers. |
| Duplicate families | Automatic duplicate warnings based on name, ID card number, village and family size. |
| Fake registrations | A different person must approve every registration before aid is given. |
| Double aid | A warning appears if the same item is given to the same family twice. |
| No accountability | Every action is written to an audit log. Edits need a reason. |
| Missed villages | Anyone can report a flooded village so teams can find out about it. |

---

## How it works

1. **Flood alerts:** villagers, local leaders or volunteers report an affected village, how many families are hit and what they need (food, clean water, shelter, medicine, rescue). Repeat reports for the same village are merged, and more reports build trust. An alert moves through *Received → Team on the way → Team reached*, and a reached village is added to the Register list.
2. **Register:** a field worker enters the family head's name, number of people, village and a landmark. Phone and ID card number are not required. Possible duplicates are flagged, and the worker can mark the record as the same household instead of creating a new one.
3. **Two-person check:** a different person (the Checker) reviews the family, confirms four points, then approves or rejects it with a reason. The person who registered a family cannot approve it. If a family moves, the Checker can update the location and the ID stays the same.
4. **ID card:** approved families receive a card with their Household ID and a QR-style code.
5. **Distribute:** the worker selects an approved family and records the aid item and quantity (rice, water, shelter kit or cash). Giving the same item twice triggers a warning.
6. **Complaints:** anyone can report a problem, such as "we were not registered", "registered but received no aid", "our information is incorrect", "we moved" or "we received less than recorded". Complaints move through *Open → Under review → Resolved*.
7. **Audit log:** every action is recorded, including registrations, checks, location changes, aid, edits, duplicate decisions, complaints and alerts. When a supervisor edits a distribution, a reason is required and both the old and new values are kept.
8. **Public page:** shows overall figures without exposing personal details such as names, phone numbers or ID numbers.

## Roles

| Role | Can do |
|---|---|
| **Field worker** (W-17, W-22) | Register families, record distributions, see and report flood alerts |
| **Checker** (V-12) | Approve or reject registrations, handle alerts and complaints, read the audit log |
| **Supervisor / Admin** (S-04) | Everything above, plus edit distribution records with a reason |
| **Public visitor** | Report flood alerts, file complaints, view the public page |

Use the **"Who are you?"** dropdown at the top of the page to switch between roles.

---

## Try the demo

1. As **W-17**, register a family called "Fatema" with 4 members in Village A. A duplicate warning appears.
2. Choose "Same household". No new record is created.
3. Register a new family, then switch to **Checker V-12** and approve it.
4. In the Check tab, move a family to a different village. The ID stays the same.
5. In Distribute, give aid. Give the same item twice to see the warning.
6. Switch to **Supervisor S-04**, edit a quantity with a reason, then open the Audit log and Public pages.

## Tech

- A single `AidTrace.html` file written in plain HTML, CSS and JavaScript.
- No framework, build step, server or database.
- Works on desktop and mobile, with light and dark themes.

## Data storage

Data is saved automatically in your browser's `localStorage`, so it survives a page refresh. It stays on that browser and device only. Use the **Reset demo** button to clear everything and restore the sample data.

## Run it

1. Download `AidTrace.html`.
2. Open it in any modern browser.

No installation is needed.

## Limitations

- The QR code is only a picture and cannot be scanned.
- The helpline and SMS options are examples and are not live.
- Data is not shared between devices.
- There is no real login. Roles are picked from a dropdown.
- It does not work offline as a full app.

## Future work

- A real backend and database
- Secure login and role management
- Real QR code generation and scanning
- Offline mode with sync
- Printable ID cards
- Multi-device and multi-team support

## License

Add your license here (for example MIT).
