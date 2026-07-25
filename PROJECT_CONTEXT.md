# Project Context — Dynamic Timetable Web App

## 📌 Project Overview & Goals
An interactive, mobile-first and desktop-optimized static Web Application for university students to customize, view, and export their timetable on **GitHub Pages**.

### Core User Features Implemented
1. **Interactive Config Wizard**:
   - Select **Section**: `Section A` or `Section B`.
   - Select **Elective 1**: `Mixed Mode VLSI Design (ECN17254)`, `Adv. Wireless Comm (ECN17251)`, or `Memory Design and Testing (ECN17256)`.
   - Select **Elective 2**: `EM interference & Compatibility (ECN17276)`, `Signal Compression Techniques (ECN17278)`, or `Organic Electronics (ECN17280)`.
2. **Persistence**:
   - Choices saved in `localStorage` (`tt_section`, `tt_el1`, `tt_el2`, `tt_theme`).
3. **Mobile Header & Navigation**:
   - **Top Row**: App title (`Weekly Timetable`) on left, compact action buttons (`📥 Image` download + `☀️` theme toggle) on right.
   - **Sub Pill**: Full-width glass pill (`Sec A · Adv Wireless... · Change`) with smooth text truncation on narrow viewports.
   - **Direct Current Day Auto-Selection on Load**:
     - `initCurrentDay()` reads `new Date().getDay()`.
     - Mon-Fri (1-5): Auto-picks current day tab (`MON`, `TUE`, `WED`, `THU`, `FRI`) and displays its vertical timeline immediately on page load.
     - Sat-Sun (6, 0): Shows Monday's upcoming schedule with a `Weekend · Upcoming Mon Schedule` indicator.
4. **Mobile Timeline View**:
   - **Day Header Meta**: Displays full day name + number of classes scheduled.
   - **Uniform Vertical Timeline**: Fixed 64px min-height cards for all hour blocks (Classes, Tutorials, Lunch, Free slots).
   - **Tutorial Badge**: Clean `Tutorial` text badge (replacing previous abbreviated `TUT` / `TUTORIAL`).
   - **Lunch Break Slot**: Matches free slot styling cleanly with simple text `Lunch Break` (no emojis/special badges).
   - Glassmorphism subject cards with subject accent color borders, location badges, code pills, and tutorial badges.
5. **Desktop Grid View**:
   - Full 5-day x 8-timeslot glassmorphism grid table (default on desktop >768px).
   - Per-subject color background tints and glowing left accent borders.
   - Glowing day indicator dots per row (`MON`, `TUE`, `WED`, `THU`, `FRI`).
   - Interactive hover scale + elevation box shadows.
   - Integrated desktop legend bar (Lecture / Tutorial / Lunch).
6. **Subject Details Modal**:
   - Clicking/tapping any class slot opens a glassmorphism popup displaying:
     - Subject Code (e.g. `ECN17101`)
     - Full Subject Name
     - Location / Room
     - Professor Name per section
7. **Export & Download (Full 5-Day Week PNG)**:
   - **Download Image**: Clicking "Download Image" / "📥 Image" on mobile or desktop generates a high-resolution, full 5-day week grid PNG screenshot (`Timetable_SecX_FullWeek.png`) via an off-screen desktop renderer.
8. **Dark / Light Theme**:
   - Theme toggle with `localStorage` persistence and glassmorphism styling.

---

## 📁 Repository Files Structure
- `timetable_data.md` — Source markdown file containing section timetables, elective schedules, and subject details. (Completed ✅)
- `data.json` — Structured JSON data used directly by the frontend web app. (Completed ✅)
- `index.html` — Single Page Application containing all UI, CSS, and JS logic (GitHub Pages ready). (Completed ✅)
- `PROJECT_CONTEXT.md` — Active context documentation for AI agents. (Updated ✅)

---

## 📑 Subject & Code Mapping
- `ECN17101`: Mobile and Wireless Communication
- `ECN17102`: Nano Electronics and Its Applications
- `ECN17254`: Mixed Mode VLSI Design (Elective 1 - Opt A)
- `ECN17251`: Advanced Wireless Communication (Elective 1 - Opt B)
- `ECN17256`: Memory Design and Testing (Elective 1 - Opt C)
- `ECN17276`: Electromagnetic Interference & Compatibility (Elective 2 - Opt A)
- `ECN17278`: Signal Compression Techniques (Elective 2 - Opt B)
- `ECN17280`: Organic Electronics (Elective 2 - Opt C)

---

## 🚦 Current Progress Status
- ✅ `timetable_data.md`: Complete.
- ✅ `data.json`: Complete.
- ✅ `index.html`: Fully updated with full `Tutorial` text badge across mobile timeline and desktop grid views.
- ✅ `PROJECT_CONTEXT.md`: Fully updated.
