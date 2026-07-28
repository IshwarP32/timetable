# Project Context — Dynamic Timetable Web App

## 📌 Project Overview & Goals
An interactive, mobile-first and desktop-optimized static Web Application for university students to customize, view, and export their timetable on **GitHub Pages**.

### Core User Features Implemented
1. **Title & Branding with Brand Icon**:
   - Updated page title and top header text to **`ECE Timetable`**.
   - Added vector SVG brand icon beside the main header title matching the Option 2B favicon design (Violet `#8b5cf6` ➔ Coral Orange `#f97316` Time Block Grid).
   - Clean action button labeled **`Download`**.
2. **Weekly Grid View Tight Vertical Layout**:
   - Wrapped grid cell contents in `.grid-cell-content` flexbox container with `gap: 3px`, bringing the Elective and Tutorial badges close to the subject name with tight, balanced proportions.
3. **Weekly Grid View Tag Order (Below Subject Name)**:
   - Positioned **`Elective`** and **`Tutorial`** badges directly **below the subject name** inside full-week grid table cells for cleaner visual hierarchy.
4. **Neutral Grey Styling for Elective Badge**:
   - Styled `.timeline-elec-badge` and `.grid-elec-tag` with a clean, neutral dark-slate/grey theme (`background: var(--bg-elevated)`, `color: var(--text-2)`), giving elective badges an aesthetic, subtle look that complements both dark and light modes.
5. **Subject Details Modal - Section A & B for Electives**:
   - Tapping any **Elective Subject** slot card opens the details popup displaying **`Section A & B`** for section, since elective classes are attended jointly by students from both sections.
   - Core section subjects continue to display `Section A` or `Section B` based on active user section.
6. **Pure LocalStorage Persistence (URL Hash Extensions Removed)**:
   - User choices (`tt_section`, `tt_el1`, `tt_el2`, `tt_theme`) are stored and retrieved **strictly via `localStorage`**.
   - Removed URL hash parameters (`#sec=...`) so the URL stays completely clean (`http://localhost/` or `https://username.github.io/repository/`).
7. **Timeline Dot Positioned Directly ON the Vertical Line**:
   - Set `.timeline-node` `left: -25px` relative to the row (`padding-left: 66px`), placing the dot center (x = 46px) **pixel-perfectly ON the vertical line** (x = 46px).
   - Maintained clean clearance between time text (0-34px), node dot (41-51px), and subject card (78px+).
8. **Restored Class Count & Weekend Subtitle**:
   - Retained the lecture count / weekend status meta line (`3 Classes Scheduled` / `Weekend · Upcoming Mon Schedule`) above the mobile timeline.
   - Removed the redundant day title text (`Monday`), relying cleanly on the active weekday tab button (`MON`, `TUE`, `WED`, `THU`, `FRI`).
9. **Clean Bottom Margin for Mobile Timeline**:
   - Added `padding-bottom: 36px` to `.today-view-container` so the mobile timeline ends with a clean margin and never touches the bottom edge of the device screen.
   - Balanced card height to `72px` and row gap `10px` for optimal vertical proportions.
10. **Generous Time Slot Label Spacing (15px Distance)**:
    - Updated `.timeline-container` `padding-left: 66px` and time label text (`width: 34px`), creating **15px of clear, generous space** between time text (e.g. `8-9`, `9-10`) and the timeline dot.
    - Maintained exact node center alignment on the vertical line.
11. **Compact Single-Screen Sidebar Drawer (No Scrolling)**:
    - Compacted vertical padding (`16px 18px`), group gaps (`12px`), title margins (`5px`), and button padding (`6px 8px`), allowing the entire sidebar panel to display at once without scrolling on desktop and mobile screens.
12. **First-Time Visit Setup Validation & Lock**:
    - On first visit (when no saved section or electives exist in `localStorage`), the **Sidebar Drawer (`#drawerOverlay`)** opens automatically on page load.
    - **Validation Requirement**: The **Apply** button remains disabled (`opacity: 0.45`, `cursor: not-allowed`), and clean text warning (`Please select Section, Elective 1, and Elective 2 to apply.`) appears until the user selects **Section + Elective 1 + Elective 2**.
    - **Lock**: The sidebar cannot be closed until all 3 required choices are made and **Apply** is clicked.
13. **Draft Preferences State & Apply Action in Sidebar**:
    - On subsequent visits, preference changes in the sidebar are held in draft state.
    - Tapping options updates draft highlights without modifying the main timetable.
    - **Clicking Apply** commits the draft preferences to active state, updates the timetable live, saves to `localStorage`, and closes the drawer.
    - **Closing without Apply** discards draft changes and preserves the active timetable untouched.
14. **Full Week Grid Vertical Height Expansion**:
    - Increased slot cell height from `66px` to **`90px`** and header/cell padding to `14px 8px`, expanding the vertical presence of the full week grid table.
15. **Favicon (Option 2B)**:
    - Modern Time Block Grid icon (`favicon.svg`) featuring a Violet-to-Coral-Orange gradient (`#8b5cf6` ➔ `#f97316`). Linked via file and SVG data URI fallback.
16. **Ultra-Clean Header Bar & Glassmorphism Sidebar Drawer**:
    - **Header Bar**: Displays SVG brand icon + `ECE Timetable` title on left + `Download` button + SVG theme toggle icon + **3-line hamburger menu button (`☰`)** on right.
    - **Slide-in Glassmorphism Drawer (`#drawerOverlay`)**: Tapping `☰` opens a drawer menu from the right edge with:
      - View mode switcher (`Today Timeline` / `Full Week Grid`).
      - Draft **Schedule Preferences** options (Section & Electives buttons).
      - **`Apply`** action button with first-time validation logic.
17. **Aesthetic SVG Theme Icons**:
    - Theme toggle button in title bar features minimalist line-art SVG Sun & Moon icons.
18. **Mobile Timeline View**:
    - **Day Header Meta**: Subtitle showing `3 Classes Scheduled` or `Weekend · Upcoming Mon Schedule`.
    - **Uniform Vertical Timeline**: Fixed 72px height cards for all hour blocks (Classes, Tutorials, Lunch, Free slots).
    - **Tutorial Badge**: Clean `Tutorial` text badge.
    - **Elective Badge**: Clean neutral grey `Elective` text badge.
    - Glassmorphism subject cards with subject accent color borders, location badges, code pills, tutorial badges, and elective badges.
19. **Desktop Grid View**:
    - Full 5-day x 8-timeslot glassmorphism grid table (default on desktop >768px).
    - Per-subject color background tints and glowing left accent borders.
    - Glowing day indicator dots per row (`MON`, `TUE`, `WED`, `THU`, `FRI`).
    - Interactive hover scale + elevation box shadows.
    - Integrated desktop legend bar (Lecture / Elective / Tutorial / Lunch).
20. **Subject Details Modal**:
    - Clicking/tapping any class slot opens a glassmorphism popup displaying:
      - Subject Code (e.g. `ECN17101`)
      - Full Subject Name
      - Location / Room
      - Section (`Section A & B` for electives)
      - Professor Name per section
21. **Export & Download (Full 5-Day Week PNG)**:
    - **Download**: Clicking "Download" on mobile or desktop generates a high-resolution, full 5-day week grid PNG screenshot (`Timetable_SecX_FullWeek.png`) via an off-screen desktop renderer.
23. **Temporary Classroom Location Changes**:
    - Supports temporary room changes defined in `data.js` via `tempLoc`.
    - Automatically displays the old classroom location with strikethrough styling (`<s>SEW1</s>`), followed by the new temporary location (`FE16`) highlighted with an amber accent badge in Mobile Timeline, Full Week Grid, and Subject Details popup.
    - Finalizing changes is done simply by updating `"loc"` and removing `"tempLoc"` in `data.js`.

---

## 📁 Repository Files Structure
- `timetable_data.md` — Source markdown file containing section timetables, elective schedules, and subject details. (Completed ✅)
- `data.js` — Single source of truth JavaScript timetable dataset loaded directly by index.html via `<script src="data.js"></script>`. (Completed ✅)
- `favicon.svg` — Option 2B (Violet -> Coral Orange Time Block Grid) vector SVG favicon. (Completed ✅)
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
- ✅ `data.js`: Updated with temporary location `tempLoc` support.
- ✅ `favicon.svg`: Complete.
- ✅ `index.html`: Fully updated with strikethrough location formatting.
- ✅ `PROJECT_CONTEXT.md`: Fully updated.
