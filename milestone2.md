# Milestone 2: Needs Finding Synthesis, Personas, Scenarios & Storyboards

## 1 Needs Finding Report

### 1.1 Overview of Research Execution

To understand how residents in compact housing acquire, store, borrow, and lend home maintenance equipment, we conducted a qualitative Needs Finding study for Toolshared. We held four 45-to-60-minute sessions that combined semi-structured interviews with contextual observation. Our participant group balanced two active tool owners who regularly lend equipment and two occasional borrowers. By transcribing these sessions and synthesizing the findings through affinity diagramming, we identified core behavioral patterns, user needs, functional system requirements, and underlying design constraints.

### 1.2 Detailed Description of Users' Needs

Visibility and Community Inventory Discovery

Residents frequently need specialized tools—such as extension ladders, orbital sanders, or pressure washers—for high-priority repair jobs. Rather than sending broad, generic inquiries across neighborhood chat groups, residents need a centralized, searchable digital inventory of equipment owned by peers in their immediate building or co-op so they can verify availability instantly.

Social Friction Reduction

Asking neighbors directly to borrow personal items creates noticeable social discomfort. Borrowers need a structured, neutral request system that establishes clear dates, project intent, and return expectations without making the exchange feel overly transactional or awkward.

Accountability and Tool Protection

While tool owners generally want to support community sharing, they worry about misplaced equipment, unannounced late returns, and damaged gear. To lend comfortably, owners need automated return reminders, calendar-bound reservations, and a quick check-in and check-out process to verify equipment condition at handoff.

Operational Guidance and Safety Notes

Inexperienced DIY borrowers need immediate access to basic operating steps, safety precautions, and consumable requirements—such as sandpaper grit or battery charging tips—provided directly by the tool owner alongside the listing.

Storage and Cost Efficiency

Modern housing layouts offer minimal extra space. Renters and homeowners need a reliable alternative to buying expensive, bulky equipment that ends up sitting unused in a tiny storage locker for 360 days out of the year.

### 1.3 Users' Current Practices

Residents currently rely on group messaging channels like WhatsApp, Facebook Groups, or Nextdoor to post borrowing requests. However, these requests get buried quickly in busy chat streams, lack searchability, offer no scheduling features, and force users to repeat manual messages for every new project. Some turn to direct door-to-door visits or direct texts, but that restricts options strictly to adjacent neighbors, carries high social friction, and fails if the neighbor is away or does not own the tool.

Others look into commercial rental platforms such as Hygglo or Fat Llama. Yet steep daily fees, mandatory insurance add-ons, and lengthy identity checks create administrative friction that clashes with informal neighborly sharing. As a last resort, residents buy tools for a single job and either scramble to find space in cramped lockers or sell them online at a loss, resulting in financial waste and storage clutter.

### 1.4 Functional Requirements (What the System Must Do)

Toolshared relies on six core capabilities to support neighborhood tool sharing:

- Searchable Community Catalog: Users can search and filter local tool inventories by category (such as Power Tools, Gardening, Ladders, or Painting), location proximity, and real-time availability status (Available, Reserved, or Borrowed).
- Digital Toolshed Profile: Tool owners can list their equipment with photos, lending guidelines, operating instructions, and accessory details.
- Date-Picker Borrowing Request Flow: Borrowers can select specific start and end dates, attach an optional project note, and submit a formal request to the owner.
- Owner Request Management: Tool owners receive immediate alerts to accept or decline borrowing requests and set pickup or return logistics.
- Condition Check-In / Check-Out Confirmation: A quick visual checklist during pickup and return logs tool condition and confirms the transfer of possession.
- Automated Deadlines & Notifications: Automated notifications send reminders ahead of scheduled pickup times and upcoming return deadlines.

### 1.5 System Constraints (What the System Should Avoid)

To protect community goodwill and maintain effortless usability, the system operates under three specific constraints:

- Avoid Mandatory Monetization & Rental Fees: The interface must not enforce commercial daily rental fees or payment gateways for standard peer-to-peer lending, preserving the spirit of neighborly cooperation.
- Avoid Screen Clutter and Complex Navigation: Interface screens must remain minimal and task-focused, avoiding multi-tier menus that slow down mobile lookups during active projects.
- Avoid Public Identity Exposure Outside Community: Personal street addresses and full inventory listings must remain visible only to verified housing community members, preventing unvetted public access.

## 2 Personas and Scenarios

###  2.1 Personas

Persona 1: Lars "The Generous Handyman" (Tool Owner / Lender)

Lars is a 42-year-old Civil Engineer living in a suburban townhouse with a small outdoor shed. 

As a skilled DIYer with an extensive personal tool collection, he is motivated by community sustainability, cutting down on overconsumption, and helping his neighbors. 

Lars needs a dependable way to track who holds his tools, monitor return dates, and trust that borrowers will treat his gear with care. He possesses high technical literacy, but gets frustrated when neighbors hold onto equipment indefinitely without staying in touch. He relies on structured approval prompts, explicit return deadlines, and automated reminders.

Persona 2: Sofia "The Space-Constrained DIYer" (Tool Borrower / Tenant)

Sofia is a 29-year-old Marketing Specialist living in a two-bedroom condo with a compact 2m² storage locker. 

She enjoys weekend home improvement projects like sanding furniture, hanging shelves, and basic gardening, but needs access to specialized gear without spending hundreds of dollars or crowding her limited storage space. Sofia has moderate technical literacy, but struggles with high social hesitation—she worries about being annoying or damaging borrowed tools. 

Clear searchable listings, transparent owner instructions, and polite digital reservation workflows make her feel comfortable borrowing.

Persona 3: Erik "The Protective Craftsman" (Experienced Tool Owner / Cautious Lender)

Erik is a 38-year-old Senior Software Engineer living in a townhouse co-op. 

He owns high-end power tools and precision woodworking equipment, including a miter saw and rotary hammer. While he wants to support community sustainability and help neighbors, 

Erik guards his expensive, finely calibrated tools closely. High technical literacy allows him to navigate digital systems easily, but he worries that borrowers might misuse delicate gear, dull blades, or break equipment without taking responsibility. He relies on custom usage guidelines (such as "Experience required"), linked operating manuals, and mandatory pre- and post-loan condition logging.

Persona 4: Thomas "The Inexperienced Emergency Fixer" (Novice Tenant / First-Time Borrower)

Thomas is a 23-year-old university student renting a room in a shared apartment. He owns no tools and has minimal DIY experience, but occasionally needs to tackle urgent tasks—like fixing a leaking pipe under his kitchen sink or mounting wall shelves—without buying gear he cannot afford or store. 

Thomas brings high digital literacy alongside low DIY literacy. He rarely knows exact technical tool names or safety precautions and feels self-conscious asking neighbors basic questions. Visual, category-based searches (like "Plumbing Basics"), owner guidance, and clear safety reminders give him the confidence to borrow and complete repairs safely.

### 2.2 Scenarios

Scenario 1: Lars Managing a Tool Request and Tracking a Loan

On Friday afternoon after finishing work at his home desk, Lars receives an email notification from Toolshared: his neighbor, Sofia, has requested his Bosch Orbital Sander for Saturday and Sunday. Lars wants to review the request, verify return dates, approve the loan, and ensure accountability. Clicking the link opens the Toolshared web app. Lars reads Sofia's project note ("Sanding a small dining table") and taps "Approve Request." He selects his preferred pickup window ("Saturday 09:00 - 10:00 AM") and adds a brief message: "Sandpaper discs are in the box; please wear safety goggles." Instantly, Toolshared shifts the sander's status from Available to Reserved, sends Sofia a pickup confirmation with Lars's address details, and schedules automated return reminders for Sunday at 5:00 PM.

#### Scenario 2: Sofia Finding, Reserving, and Picking Up a Tool

On Thursday evening, Sofia sits in her condo living room planning a weekend furniture restoration project. She needs to find an orbital sander within her housing association without buying new equipment. Opening Toolshared on her laptop, Sofia types "Sander" into the search bar and filters results by "Available This Weekend." Lars's Bosch Orbital Sander appears at the top of the list, located just 150 meters away. Sofia reviews the tool profile, checks Lars's notes, selects Saturday and Sunday on the calendar picker, and submits her request with a short note. On Friday evening, she receives notification that Lars approved the request. At 9:15 AM on Saturday, she walks to Lars's townhouse, collects the sander in its carry case, and taps "Confirm Pickup" on her phone to log that the equipment arrived in good working order. The app updates the tool status to Borrowed, logs the timestamped confirmation, and sets a return reminder for Sunday afternoon.

#### Scenario 3 (Standard Return): Returning the Borrowed Tool & Completing the Loan Cycle

At 4:45 PM on Sunday, Sofia wraps up her furniture project in her apartment and prepares to return the sander, log its condition, and close out the loan. Sofia cleans the sander body and packs the sandpaper discs back into the carry case. A push notification alerts her: "Reminder: Return Bosch Sander to Lars by 18:00." Tapping "Initiate Return" in the app, she checks off "Tool Cleaned & Complete" and walks over to Lars's townhouse. Lars inspects the sander and taps "Confirm Return & Good Condition" on his phone screen. Toolshared immediately shifts the sander back to Available in the catalog, logs the return timestamp, and sends both users a confirmation note thanking them for participating in community tool sharing.

#### Scenario 4 (Edge Case 1): Handling Tool Damage or Fault During Return

On Saturday afternoon, Thomas is mounting shelves in his apartment when a driver bit strips and the drill chuck sticks. He needs to report accidental damage honestly and resolve repairs without damaging neighborly trust. Rather than returning the tool quietly, Thomas opens Toolshared and selects "Report Damage / Issue" on his active loan card. He uploads a photo of the stripped bit and explains what happened, triggering an immediate alert on Erik's phone. When Thomas arrives to return the drill, Erik appreciates his upfront disclosure. They walk through the guided resolution prompt in the app and agree that Thomas will purchase a $10 replacement driver bit pack. Erik logs "Returned with Minor Damage — Resolution Agreed" in the system, which marks the drill as In Maintenance in the catalog until Erik confirms the bit has been replaced.

#### Scenario 5 (Edge Case 2): Managing Overdue Returns & Extension Requests

At 4:00 PM on Sunday, Sofia realizes her furniture project requires an extra coat of stain and light sanding on Monday morning. Her reservation expires in two hours, and she wants to extend the loan by 24 hours without creating scheduling conflicts or frustrating Lars. Instead of keeping the tool past the deadline or making an awkward phone call, Sofia opens Toolshared and taps "Request 1-Day Extension." The system verifies that Lars has no upcoming bookings for the sander and routes an urgent request to his phone: "Sofia requested a 1-day extension until Monday 18:00." Lars taps "Approve Extension," automatically updating the reservation end date to Monday at 18:00, clearing overdue warnings, and adjusting Lars's calendar seamlessly.

#### Scenario 6 (Edge Case 3): Handling Partial Return with Missing Accessories

On Sunday evening, Thomas drops off a borrowed tile cutter at Lars's doorstep. During handoff, both parties need to identify missing components and agree on a plan to recover them. Thomas hands the tile cutter back to Lars at the door. Lars runs through the itemized digital checklist on his phone ("Tile Cutter Body, Cutting Wheel, Water Reservoir Cap, Power Adapter") and notices the power adapter is missing. Thomas realizes he left it plugged in near his kitchen counter. Lars taps "Incomplete Return — Missing Component: Power Adapter," setting the loan status to Pending Return — Missing Parts. Toolshared then sends Thomas an automated push reminder to drop off the missing adapter the following morning to finalize the return.

## 3 Design Concept Storyboards

### 3.1 Storyboard 1: Tool Discovery and Reservation Request (Sofia's Workflow)

Sofia stands in her apartment looking at a worn wooden dining table, holding a sheet of manual sandpaper and realizing hand-sanding will take days. She opens the Toolshared web app on her laptop and types "Orbital Sander" into the main search bar. The screen displays category results filtered by "Housing Co-Op Area A" and "Available This Weekend," highlighting Lars's Bosch Orbital Sander with a green Available tag. Sofia clicks the card to review tool photos, owner lending rules, and safety guidance ("Includes dust collector"). Tapping the calendar picker, she selects Saturday and Sunday, adds a short note ("Refinishing dining table"), and clicks "Submit Borrowing Request." A green banner confirms "Request Sent to Lars! Pending Approval," letting her know her reservation is in motion.

### 3.2 Storyboard 2: Request Review, Approval, and Pickup Setup (Lars's Workflow)

While working at his desk, Lars receives a notification on his phone: "New Request: Sofia wants to borrow your Bosch Sander." Tapping the alert opens the Request Review screen, where he checks Sofia's profile, project note, and requested dates. Lars clicks "Approve Request," picks his preferred pickup window ("Saturday 09:00 - 10:00 AM"), and adds a note explaining where the extra accessories are stored. Toolshared updates the tool status to Reserved and generates a pickup pass with contact details. Lars packs the sander and sandpaper box into its carry case near his front door, while Sofia receives a push notification confirming her pickup for Saturday at 09:00 AM at Unit 4B.

### 3.3 Storyboard 3: Hand-Off, Condition Check-In, and Return (Accountability Workflow)

On Saturday morning, Sofia arrives at Lars's doorstep, where Lars greets her and hands over the sander carry case. Sofia opens Toolshared on her phone, taps "Confirm Pickup," and checks off "Tool & Accessories Received in Good Condition." Over the weekend, she sands her dining table in her workspace. At 4:30 PM on Sunday, her phone alerts her: "Reminder: Return Bosch Sander to Lars by 6:00 PM today." Sofia wipes down the sander, packs it into its case, and returns it to Lars at 5:30 PM. Lars taps "Confirm Tool Returned" on his phone, and Toolshared updates the sander back to Available in the community catalog, completing the loan cycle.
