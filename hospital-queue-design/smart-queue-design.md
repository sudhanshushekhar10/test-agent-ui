# Smart Queue Ticket Interface Design

## Overview
This document outlines the design for a hospital Smart Queue Ticket feature that allows patients to book queue tickets online, track their position in real-time, and receive notifications when their turn approaches.

## Design Philosophy
The interface is designed with simplicity and accessibility in mind, ensuring users of all age groups and technical abilities can navigate the system with ease. A minimal color scheme focuses attention on important elements while maintaining a clean, uncluttered appearance.

## Color Scheme
- **Primary Color**: #1976D2 (Accessible blue)
- **Secondary Color**: #4CAF50 (Green for positive actions)
- **Warning Color**: #FF9800 (Orange for alerts)
- **Background Color**: #FFFFFF (White)
- **Text Color**: #333333 (Dark gray)

## Typography
- **Primary Font**: San Francisco (iOS) / Roboto (Android)
- **Sizes**: 
  - Large (Headers): 20-24px
  - Medium (Buttons): 16-18px
  - Small (Body): 14-16px
  - Extra Small (Supporting text): 12px
- **Font weights**: Normal and Bold only

## Wireframes

### 1. Home Screen
```
┌──────────────────────────────────┐
│ Hospital Name             [icon] │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────┐    │
│  │    BOOK QUEUE TICKET     │    │
│  └──────────────────────────┘    │
│                                  │
│  YOUR RECENT BOOKINGS            │
│  ┌──────────────────────────┐    │
│  │ Dr. Smith - Cardiology   │    │
│  │ Today, 2:30 PM  ●ACTIVE  │    │
│  └──────────────────────────┘    │
│                                  │
│  ┌──────────────────────────┐    │
│  │ Dr. Jones - Orthopedics  │    │
│  │ 15 Aug, 10:00 AM ●DONE   │    │
│  └──────────────────────────┘    │
│                                  │
│                                  │
│                                  │
├──────────────────────────────────┤
│ [Home] [Queue] [Appointments] [Profile] │
└──────────────────────────────────┘
```

**Key Elements:**
- Prominent "BOOK QUEUE TICKET" button with high contrast
- Recent bookings list with status indicators
- Simple navigation bar with clear icons and labels
- High contrast between text and background
- Sufficient touch target sizes (minimum 44×44 pixels)

### 2. Queue Booking Screen
```
┌──────────────────────────────────┐
│ ← Book Queue Ticket              │
├──────────────────────────────────┤
│                                  │
│  Step 1 of 3                     │
│  ○───○───○                       │
│                                  │
│  SELECT DEPARTMENT               │
│                                  │
│  ┌──────────────────────────┐    │
│  │ Cardiology          ▼    │    │
│  └──────────────────────────┘    │
│                                  │
│  SELECT DOCTOR                   │
│                                  │
│  ┌──────────────────────────┐    │
│  │ Dr. Smith (Available)    │    │
│  └──────────────────────────┘    │
│  ┌──────────────────────────┐    │
│  │ Dr. Brown (Available)    │    │
│  └──────────────────────────┘    │
│                                  │
│  SELECT TIME SLOT                │
│                                  │
│  ┌───┐ ┌───┐ ┌───┐ ┌───┐ ┌───┐  │
│  │9:00│ │9:30│ │10:00│ │10:30│  │
│  └───┘ └───┘ └───┘ └───┘ └───┘  │
│                                  │
│  ┌──────────────────────────┐    │
│  │         CONTINUE         │    │
│  └──────────────────────────┘    │
│                                  │
├──────────────────────────────────┤
│ [Home] [Queue] [Appointments] [Profile] │
└──────────────────────────────────┘
```

**Key Elements:**
- Clear step indicator showing progress
- Large, easy-to-select dropdown for departments
- Visual distinction between available/unavailable doctors
- Time slot selection with adequate spacing
- Back navigation option
- Prominent "Continue" button

### 3. Booking Confirmation Screen
```
┌──────────────────────────────────┐
│ ← Booking Confirmation           │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────┐    │
│  │       TICKET BOOKED      │    │
│  │                          │    │
│  │         #A045            │    │
│  │                          │    │
│  │    Estimated Wait Time   │    │
│  │       45 minutes         │    │
│  └──────────────────────────┘    │
│                                  │
│  BOOKING DETAILS                 │
│  Department: Cardiology          │
│  Doctor: Dr. Smith               │
│  Date: Today, 17 Aug 2025        │
│  Time: 10:00 AM                  │
│                                  │
│  ┌──────────────────────────┐    │
│  │ Notify when turn is near │    │
│  │  ○───────────● ON        │    │
│  └──────────────────────────┘    │
│                                  │
│  ┌──────────────────────────┐    │
│  │     VIEW QUEUE STATUS    │    │
│  └──────────────────────────┘    │
│                                  │
│  ┌──────────────────────────┐    │
│  │     BACK TO HOME         │    │
│  └──────────────────────────┘    │
│                                  │
├──────────────────────────────────┤
│ [Home] [Queue] [Appointments] [Profile] │
└──────────────────────────────────┘
```

**Key Elements:**
- Prominently displayed ticket number
- Clear estimated wait time information
- Concise summary of booking details
- Simple ON/OFF toggle for notifications
- Two clear action buttons with distinct visual hierarchy
- Adequate spacing between elements

### 4. Live Queue Status Screen
```
┌──────────────────────────────────┐
│ ← Queue Status                   │
├──────────────────────────────────┤
│                                  │
│  ┌──────────────────────────┐    │
│  │ YOUR TURN IS APPROACHING │    │
│  │   Please be ready!       │    │
│  └──────────────────────────┘    │
│                                  │
│  YOUR POSITION                   │
│                                  │
│  ┌──────────────────────────┐    │
│  │      You are #3          │    │
│  │      in the queue        │    │
│  └──────────────────────────┘    │
│                                  │
│  QUEUE PROGRESS                  │
│  ┌──────────────────────────┐    │
│  │ [====>--------]  6/10    │    │
│  └──────────────────────────┘    │
│                                  │
│  ESTIMATED WAIT TIME             │
│  ┌──────────────────────────┐    │
│  │     15 minutes           │    │
│  └──────────────────────────┘    │
│                                  │
│  CURRENT TICKET: #A042           │
│                                  │
│  ┌──────────────────────────┐    │
│  │       CANCEL TICKET      │    │
│  └──────────────────────────┘    │
│                                  │
├──────────────────────────────────┤
│ [Home] [Queue] [Appointments] [Profile] │
└──────────────────────────────────┘
```

**Key Elements:**
- Attention-grabbing alert when turn is approaching
- Clear position indicator
- Visual progress bar showing queue movement
- Updated estimated wait time
- Information on current ticket being served
- Option to cancel if needed
- Auto-refresh indicator or manual refresh button (not shown)

## Design Justification

1. **Accessibility-First Approach**: The design follows WCAG 2.1 guidelines with high contrast ratios (minimum 4.5:1 for text), large touch targets (44×44px minimum), and clear visual hierarchy. This ensures users of all ages and abilities, including elderly patients common in hospital settings, can navigate the app without difficulty.

2. **Progressive Disclosure Pattern**: Information is presented in logical steps (department → doctor → time) following the Nielsen Norman Group's principle of progressive disclosure, reducing cognitive load and decision fatigue particularly important in healthcare scenarios where users may already be stressed.

3. **Status Visibility & Feedback**: The design incorporates real-time status updates and clear notifications following Jakob Nielsen's visibility of system status heuristic, keeping users informed about their position and estimated wait time, which reduces anxiety in medical waiting situations.

4. **Minimalist Design**: Following principles from both Material Design and Apple's Human Interface Guidelines, the interface uses a limited color palette (3-4 colors), ample white space, and only essential information to create a calm, uncluttered experience appropriate for a potentially stressful context.

5. **Consistent Navigation & Mental Models**: The interface maintains consistent navigation patterns and familiar UI components (toggles, progress bars, lists) that match platform conventions, helping users leverage existing mental models and reducing learning curve for less tech-savvy patients.
