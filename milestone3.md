## Section 1: System Inputs, Outputs &amp; System State Mapping

### 1.1 User-Provided Data Inputs

* **Tool Search Queries &amp; Keyword Filtering:** Free-form text input entered into the primary search bar to query the community database by tool name, brand, or model (e.g., "Orbital Sander", "Bosch", "Extension Ladder").
* **Category &amp; Attribute Selections:** Multi-select checkboxes and dropdown menus used to filter listings by category (e.g., Power Tools, Gardening, Painting &amp; Ladders, Plumbing), distance radius (e.g., within 500m, same co-op building), and tool power source (e.g., Cordless Battery, Corded Electric, Manual).
* **Date-Picker Reservation Ranges:** Interactive calendar UI component allowing borrowers to select specific start and end dates/times for tool reservations.
* **Borrower Project &amp; Usage Context Notes:** Text field accompanying borrowing requests where users explain their intended DIY project (e.g., "Sanding dining room table"), helping owners evaluate appropriateness and safety.
* **Tool Profile Entry Data:** Form input fields completed by tool owners when cataloging an item, including tool title, category dropdown, condition rating (e.g., Excellent, Good, Fair), custom lending rules (e.g., "Experience required with miter saws"), included accessories checklist (e.g., "2x 18V batteries, charger, carry case"), and digital photo uploads.
* **Doorstep Hand-Off &amp; Condition Check-In Inputs:** Checkbox confirmations completed during physical equipment transfer verifying that the tool is undamaged, clean, and all listed accessories are present.
* **Damage &amp; Issue Reporting Inputs:** Text description and photo attachment fields used during return if a tool is damaged, malfunctioning, or returned with missing components.

### 1.2 External &amp; Automated Inputs

* **Verified Community Membership Credentials:** Authentication token and location verification confirming the user resides within a recognized housing co-op or neighborhood association boundary.
* **Timestamped System Logs:** Automated system clock inputs that record exact times for request submissions, owner approvals, doorstep check-ins, and return completions.
* **Automated Calendar Conflict Detection:** System verification checking existing tool reservations against requested date ranges to prevent double-booking.

### 1.3 System Outputs &amp; Feedback Mechanisms

* **Real-Time Inventory Status Badges:** Color-coded visual indicators displaying tool availability on catalog cards (*Available* [Green], *Reserved* [Yellow], *Borrowed* [Blue], *In Maintenance* [Red]).
* **Filtered Community Catalog Display:** Dynamic grid and list views updating results instantaneously based on search queries, category selections, and weekend availability filters.
* **Digital Pickup &amp; Hand-Off Pass:** Visual confirmation screen generated upon owner approval, summarizing pickup address, agreed time window, owner contact details, and accessory checklist.
* **Automated Push &amp; SMS Notifications:** System-generated alerts dispatched to borrowers and owners for pending requests, pickup reminders, and 24-hour/2-hour return deadline warnings.
* **Accountability &amp; Transaction History:** Activity log summarizing a user's sharing stats (e.g., "12 tools shared, 100% on-time returns") to build community trust.

### 1.4 System State &amp; Logic Variable Mapping

* **Unauthenticated Visitor State:** Read-only access to public landing page and general tool concept overview; search actions prompt community verification login.
* **Active Borrower State:** User has an active request or ongoing loan; header displays persistent status bar with countdown timer to return deadline and quick link to return checklist.
* **Active Owner State:** Owner has pending borrowing requests or out-on-loan tools; dashboard highlights pending approvals and upcoming doorstep handoffs.
* **Item State Transitions:**  
  * *Available* $ ightarrow$ *Pending Approval* (when borrower submits request)
  * *Pending Approval* $ ightarrow$ *Reserved* (when owner approves request)
  * *Reserved* $ ightarrow$ *Borrowed* (when doorstep check-in is confirmed)
  * *Borrowed* $ ightarrow$ *Available* (when return check-in is finalized without issues)
  * *Borrowed* $ ightarrow$ *In Maintenance* (if damage or missing parts are reported during return)

---

## Section 2: 10 Low-Fidelity Screen Wireframe Layouts

### Screen 1: Homepage / Unauthenticated Landing Page

* **Layout Structure:** Single-column responsive layout with top global navigation bar, prominent hero section, and 3-column feature overview below.
* **Navigation &amp; Header:** Top bar features Toolshared logo on left, community selector dropdown ("Skagen Co-Op Community A"), and "Sign In / Join" button on right.
* **Main Content Area:** Hero section contains large headline ("Borrow Tools From Neighbors You Trust"), explanatory subtitle, and prominent central search bar with an integrated search button.
* **Body Elements:** Below search bar, horizontal category filter chips (*Power Tools*, *Gardening*, *Ladders*, *Cleaning*) allow one-tap filtering. A grid below showcases 4 featured community listings with thumbnail photo, tool title, owner first name, distance (e.g., "120m away"), and green *Available* badge.

### Screen 2: Search Results &amp; Community Catalog Filtering Page

* **Layout Structure:** Two-column desktop / single-column collapsible mobile layout with left-hand filter sidebar and right-hand catalog results grid.
* **Filter Controls Sidebar:** Top search input box, category multi-select checkboxes, date-picker input ("Available Between [Date] and [Date]"), and distance slider ("Within 500m").
* **Results Header:** Displays total match count ("14 Tools Found in Skagen Co-Op") and sort dropdown (*Distance: Nearest First*, *Recently Added*, *Tool Name*).
* **Listing Cards Grid:** Each tool card displays a 16:9 item photo, prominent tool title, category tag, owner avatar with first name, proximity distance, real-time availability status badge, and primary action button ("View &amp; Borrow").

### Screen 3: Tool Detail &amp; Reservation Booking Page

* **Layout Structure:** Two-column page layout with large media/info section on left and fixed reservation booking card on right.
* **Tool Detail Column (Left):** Primary tool photo carousel, bold title ("Bosch Orbital Sander PSS 250 AE"), category breadcrumb, owner profile tile ("Lars V. — 100% Return Rating"), item description, included accessories list (batteries, dust box, carry case), and owner usage/safety guidelines ("Requires safety goggles").
* **Reservation Card (Right):** Prominent inline calendar date-picker allowing selection of start and end dates, estimated loan duration calculation, free borrowing fee confirmation ("$0.00 — Non-Monetized Loan"), multi-line text input for "Project Note to Owner", and primary call-to-action button ("Submit Borrowing Request").

### Screen 4: Borrower Request Confirmation &amp; Status Screen

* **Layout Structure:** Centered single-card confirmation modal layout with clear visual hierarchy.
* **Header Banner:** Prominent green success checkmark icon with headline "Request Submitted to Lars!"
* **Reservation Summary:** Structured summary box displaying requested tool name, selected dates (e.g., "Sat Oct 24, 09:00 — Sun Oct 25, 18:00"), owner name, and project note excerpt.
* **Next Steps &amp; Guidance:** Numbered instructions explaining what happens next ("1\. Lars will review your request. 2\. You will receive an alert with pickup instructions once approved.").
* **Action Buttons:** Secondary "Add to Calendar" button and primary "Go to My Borrowed Tools" dashboard link.

### Screen 5: Tool Owner "My Toolshed" Management Dashboard

* **Layout Structure:** Dashboard layout with top summary metrics cards, tabbed navigation, and primary tool inventory table below.
* **Metric Cards Bar:** 3 metric tiles displaying *Total Tools Listed* (e.g., 6), *Active Loans* (1), and *Community Shares* (14 loans completed).
* **Action Header:** Primary "+ Add New Tool" button prominently placed top-right.
* **Inventory Table / List:** Rows listing each owned tool with thumbnail image, tool name, category, current status badge (*Available*, *Reserved*, *Borrowed*), borrower name if out on loan, expected return date, and "Manage" dropdown menu (*Edit Listing*, *Pause Lending*, *Remove*).

### Screen 6: Add / Edit Tool Form Screen

* **Layout Structure:** Centered single-column form with grouped field sets and bottom sticky action bar.
* **Form Sections:**  
  * **Basic Info:** Text input for Tool Name, category selection dropdown, and brand/model text field.
  * **Media Upload:** Photo attachment box supporting drag-and-drop or camera capture.
  * **Lending Parameters:** Radio buttons for lending rules (*Open to All Neighbors*, *Experience Required*), text area for "Usage &amp; Safety Guidelines", and multi-select checklist for included accessories.
  * **Condition &amp; Location:** Dropdown for tool condition rating (*Like New*, *Good*, *Fair*) and storage locker location note.
* **Footer Actions:** Secondary "Cancel" button and primary "Save &amp; Publish Tool" button.

### Screen 7: Owner Request Review &amp; Pickup Setup Screen

* **Layout Structure:** Focused task screen displaying borrower credentials, project context, and interactive approval controls.
* **Borrower Info Header:** Borrower profile card displaying photo, name ("Sofia N."), community address ("Building B, Apt 302"), and past borrowing history ("4 successful loans").
* **Project Context Box:** Highlighted callout box displaying Sofia's project note ("Sanding down a wooden dining table over the weekend").
* **Pickup Logistics Selector:** Interactive time-window selector dropdown ("Saturday morning 09:00 - 10:00 AM") and text area for "Pickup Instructions / Doorbell Notes".
* **Decision Buttons:** Red outline "Decline Request" button and prominent green "Approve &amp; Set Pickup" button.

### Screen 8: Doorstep Hand-Off &amp; Condition Check-In Screen

* **Layout Structure:** Mobile-optimized mobile webview designed for doorstep interaction.
* **Header &amp; Status:** Headline "Doorstep Hand-Off: Bosch Orbital Sander", displaying owner (Lars) and borrower (Sofia) names.
* **Interactive Inspection Checklist:**  
  * [x] Tool body inspected — no visible cracks or cord damage
  * [x] Battery &amp; charger unit included
  * [x] Carry case and safety goggles present
  * [x] Borrower understands basic operating instructions
* **Digital Confirmation:** Large touch-friendly button "Confirm Hand-Off &amp; Start Loan", which updates system state to *Borrowed* and timestamps the transfer.

### Screen 9: Tool Return &amp; Inspection Confirmation Screen

* **Layout Structure:** Mobile-optimized return workflow screen with condition verification and optional issue flagging.
* **Return Header:** Headline "Return Confirmation: Bosch Orbital Sander".
* **Condition Verification Prompt:** Radio selection (*Returned in Good Condition*, *Minor Wear / Cleaned*, *Damaged or Missing Parts*).
* **Issue Reporting Trigger (If Damaged/Missing Selected):** Expands text box for damage description and photo upload input for recording broken components.
* **Final Sign-Off:** Dual confirmation button ("Complete Return &amp; Re-List as Available") that resets tool status back to *Available* and prompts mutual star rating.

### Screen 10: Communal / HOA Admin Dashboard

* **Layout Structure:** Multi-widget administrative dashboard for housing association board members and shared asset managers.
* **Header:** Title "Skagen Co-Op Communal Assets &amp; Toolshed", displaying active community members (48 registered residents).
* **Shared Equipment Table:** Tracks HOA-owned heavy equipment (e.g., Lawn Aerator, Industrial Pressure Washer) with columns for Asset ID, Current Location/Holder, Maintenance Status, and Last Serviced Date.
* **Management Controls:** Buttons for "Export Usage Audit Log", "Flag Asset for Repair", and "Add HOA Asset".

---

## Section 3: Paper Prototype &amp; Usability Evaluation Plan

### 3.1 Paper Prototype Setup &amp; Interactive Manipulations

* **Physical Materials:** High-contrast hand-drawn screen templates on 8.5"x11" cardstock, representing mobile and desktop viewports.
* **Dynamic Overlays &amp; Sticky Manipulations:**  
  * **Pop-Up Calendar Picker:** Small paper calendar overlay placed over Screen 3 when the user taps the date input field.
  * **Dropdown Sliders &amp; Filters:** Movable paper strips pulled through frame slots to simulate category dropdowns and distance sliders on Screen 2.
  * **Status Badge Swaps:** Reusable sticky-note badges (*Available*, *Reserved*, *Borrowed*) placed on catalog listings and dashboard rows to simulate real-time state changes.
  * **System Alert Banners:** Paper sliding banners ("Request Submitted", "Return Reminder Dispatched") positioned at the top of screens following action button taps.
* **Facilitator &amp; Computer Roles:**  
  * **Facilitator:** Introduces the Toolshared concept, presents scenario instructions, prompts think-aloud reflections, and conducts post-test debriefs without giving hints.
  * **"The Computer":** Manually swaps paper screens, attaches sticky note overlays, updates status badges, and writes dummy user inputs onto form fields in real time based on user taps.

### 3.2 Supported Tasks &amp; Detailed Interaction Sequences

#### Task 1: Borrower Finding, Filtering, and Submitting a Tool Request

* **Goal:** Locate an orbital sander in the local co-op, filter for weekend availability, select dates, add a project note, and submit a borrowing request.
* **Interaction Sequence (6 Interactions):**  
  1. *Interaction 1:* Tap the central search bar on Screen 1 (Homepage) and type "Sander".
  2. *Interaction 2:* Tap "Filter by Category" on Screen 2 and select the "Power Tools" checkbox.
  3. *Interaction 3:* Tap "Available Dates" field and select "Saturday Oct 24 to Sunday Oct 25" on the paper pop-up calendar overlay.
  4. *Interaction 4:* Tap "View &amp; Borrow" on Lars's Bosch Orbital Sander card to open Screen 3 (Tool Detail).
  5. *Interaction 5:* Tap the "Project Note" text box and type "Refinishing dining table".
  6. *Interaction 6:* Tap the primary "Submit Borrowing Request" button, triggering transition to Screen 4 (Confirmation).

#### Task 2: Tool Owner Reviewing Request, Setting Pickup Details, and Approving

* **Goal:** Receive a request notification, review borrower context, specify a doorstep pickup time window, add safety instructions, and approve the loan.
* **Interaction Sequence (5 Interactions):**  
  1. *Interaction 1:* Tap the incoming "New Request" paper alert banner on Screen 5 (Owner Dashboard).
  2. *Interaction 2:* Read borrower profile (Sofia) and project note on Screen 7 (Request Review).
  3. *Interaction 3:* Tap "Pickup Time Window" dropdown and select "Saturday 09:00 - 10:00 AM".
  4. *Interaction 4:* Tap "Owner Instructions" box and type "Sandpaper discs in box; wear goggles".
  5. *Interaction 5:* Tap primary "Approve &amp; Set Pickup" button, updating the sander's sticky badge from *Available* to *Reserved*.

#### Task 3: Conducting Hand-off, Doorstep Condition Check-In, and Final Return

* **Goal:** Complete doorstep check-in upon collecting the tool, use the tool, and finalize return inspection with the owner.
* **Interaction Sequence (6 Interactions):**  
  1. *Interaction 1:* Open Screen 8 (Doorstep Hand-Off View) on smartphone upon arriving at owner's door.
  2. *Interaction 2:* Check off items on inspection checklist (*Body OK*, *Batteries Included*, *Goggles Present*).
  3. *Interaction 3:* Tap "Confirm Hand-Off &amp; Start Loan", shifting status to *Borrowed*.
  4. *Interaction 4:* Tap "Initiate Return" button on Screen 8 upon completing the project on Sunday.
  5. *Interaction 5:* Select "Returned in Good Condition" radio button on Screen 9 (Return Screen).
  6. *Interaction 6:* Tap "Complete Return &amp; Re-List", resetting tool status back to *Available*.

### 3.3 Usability Testing Execution &amp; Observer Findings

* **Testing Setup:** Paper prototype evaluations conducted with 2 representative participants (1 resident tool owner and 1 apartment tenant borrower) using a think-aloud protocol.
* **Key Behavioral Observations:**  
  * **Unclear Free Lending Model:** On Screen 3 (Tool Detail), both participants hesitated at the booking box looking for a daily rental fee or credit card field, initially assuming Toolshared was a commercial rental app like Hygglo.
  * **Calendar Picker Friction:** On Screen 3, participants tried tapping dates directly on a static display before realizing they needed to tap the input field to trigger the pop-up calendar.
  * **Doorstep Checklist Reluctance:** During Task 3 (Hand-Off), the borrower participant expressed concern that filling out a detailed 6-item checklist at the owner's doorstep might feel social awkward or rude to the neighbor waiting at the door.
  * **Missing Extension Workflow:** When reviewing the return screen, the borrower asked, "What if my project isn't finished on Sunday? Where do I ask for more time?"
  * **HOA Admin Access Confusion:** The owner participant wondered how communal tools owned by the housing board differed from personal tools in the neighborhood catalog.

### 3.4 5 Strategic Iterative Design Changes

Based on observer notes and participant feedback during paper prototype testing, the following 5 concrete UI improvements were made:

1. **Explicit "100% Free / Peer-to-Peer" Banner Added to Booking Card (Screen 3):**  
  * *Problem Encountered:* Users hesitated during booking, expecting hidden commercial rental fees or mandatory payment fields.
  * *UI Fix:* Added a prominent green badge reading "$0.00 — Free Community Loan (No Rental Fees)" directly above the reservation button on Screen 3.
2. **Simplified 2-Tap Doorstep Hand-Off Checklist (Screen 8):**  
  * *Problem Encountered:* Participants felt a lengthy 6-item inspection checklist at the owner's front door created social awkwardness.
  * *UI Fix:* Streamlined the doorstep check-in on Screen 8 to a single master toggle ("Tool &amp; Listed Accessories Present &amp; Undamaged") with an optional "Report Pre-existing Damage" link.
3. **Integrated "Request 24-Hour Extension" Button on Active Loan Screen (Screen 8 &amp; 9):**  
  * *Problem Encountered:* Borrowers had no clear digital pathway if a weekend DIY project ran over time, forcing awkward phone calls.
  * *UI Fix:* Added a "Request Extension" button on the active loan status bar, allowing borrowers to request additional time with one tap for owner approval.
4. **Interactive Inline Calendar Picker Replacement (Screen 3):**  
  * *Problem Encountered:* Users tried tapping calendar days directly on static summary text rather than opening the date field.
  * *UI Fix:* Replaced the dropdown text field on Screen 3 with a permanently expanded inline calendar widget where available dates are highlighted in light green.
5. **Distinct "HOA Communal Asset" Badge on Catalog Listings (Screen 2 &amp; Screen 10):**  
  * *Problem Encountered:* Users could not distinguish between tools owned by individual neighbors versus shared equipment stored in the HOA central shed.
  * *UI Fix:* Added a distinct blue "HOA Communal Asset" badge on listing cards, indicating items stored in the communal shed with automated locker access code delivery upon approval.
