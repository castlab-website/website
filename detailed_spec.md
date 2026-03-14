# CAST Laboratory Website - Detailed Specification

This document provides a highly detailed specification for an AI agent to implement the CAST (Connected Autonomous Safe Technologies) lab website at Texas A&M University. It combines the high-level requirements from the initial spec with the visual layout and aesthetic guidelines from the design document.

## 1. Global Requirements & Tech Stack

*   **Goal:** A modern, professional, yet flashy and engaging website for the CAST lab.
*   **Accessibility:** Fully responsive (desktop and mobile), easy to navigate, and scalable.
*   **Maintainability:** Easy to add new projects, team members, and publications. Component reusability (Header, Footer, Cards) is required.
*   **Tech Stack:** 
    *   **Astro** is the chosen framework, as it will be ideal for serving a high-performance, entirely static website while still allowing reusable component-based development.  

## 2. Visual Language & Aesthetics

*   **Color Palette (Official University Colors):**
    *   Primary Maroon: `#500000` (Header, Footer, accented backgrounds)
    *   Secondary Maroon: `#732f2f` (Hover states, subtle gradients, secondary accents)
    *   White: `#FFFFFF` (Primary text against maroon, card backgrounds)
    *   Light Gray: `#EAEAEA` or `#F4F4F4` (Section backgrounds avoiding stark white)
    *   Dark Maroon / Card Backgrounds: e.g., `#3D0000` for cards on a maroon background to create depth.
*   **Typography:**
    *   *Headings:* **Oswald** (Official University Font). Often uppercase for navigation, bold, and narrow.
    *   *Body Text:* **Work Sans** (as referenced in design) or a similarly clean, modern sans-serif. **Note:** The design should be built in a way (e.g., using CSS variables) that makes it trivial to swap all fonts to Oswald globally if that decision is made later.
    *   *Nav Links:* Uppercase, generous letter spacing.
*   **Dynamic Effects:**
    *   "Flashy yet professional": Smooth scrolling, subtle fade-ins on load.
    *   *Hover Effects:* 
        *   **Home Page Circles ("What We're Working On"):** On hover, the image should enlarge slightly, but it should **not** gray out.
        *   **Research Page Project Cards:** On hover, the image should enlarge slightly and gray out, revealing descriptive text layered over the image.
    *   Buttons ("All News", "Learn More") should have a scale or color-shift animation. 

## 3. Site Architecture & Layout

### 3.1 Global Header (Navigation)
*   **Layout:** Full-width, fixed/sticky at the top.
*   **Left Side:** Texas A&M Engineering Logo (White version over maroon background).
*   **Right Side:** Navigation links (`HOME`, `RESEARCH`, `PEOPLE`, `PUBLICATIONS`).
*   **Mobile:** Collapses into a responsive hamburger menu.

### 3.2 Global Footer
*   **Background:** Primary Maroon (`#500000`).
*   **Content:** 
    *   Lab Title: "CAST - Connected Autonomous Safe Technologies Laboratory @ Texas A&M University" (large, bold, white).
    *   Contact Info: Mailing Address and Email.
    *   Copyright or useful links on the bottom line.

### 3.3 Pages Breakdown

#### A. Home Page
*   **Hero Section:** Full-width background image of a Navistar truck (platooning technology). Text overlay on the left: four large blocks containing "CONNECTED", "AUTONOMOUS", "SAFE", "TECHNOLOGIES" in stacked, semi-transparent maroon boxes, plus "At CAST Lab" subtitle.
*   **"What We're Working On" Section:** Dark maroon background with 3 horizontal circular project placeholders, featuring labels underneath. 
    *   *Interaction:* Hovering over these circles should enlarge the photo slightly. It should **not** gray out.
*   **"Latest News & Publications" Section:** Two-column layout. Left column has a list of 3 recent publication cards. Right column has a large image (e.g., CASTbot) with a ribbon-style "All News" button.

#### B. Research (Projects) Page
*   **Header:** "Our Research Projects !" (Large, bold, serif/slab-serif).
*   **Project Grid:** Responsive 3-column grid on desktop, single column on mobile.
*   **Project Cards:** Each card has an image at the top with rounded corners. A maroon footer block at the bottom contains the title in white text. 
    *   *Interaction:* The hover effect (photo zoom, grayscale, text overlay) should be implemented here.

#### C. Project Detail Page (Dynamic Route)
*   **Layout:** Single column, focused on readability.
*   **Header:** Full-width header image with rounded corners.
*   **Content Layout:** Sections for "What is [Project]?" and "Why is it needed?" using maroon background boxes with "chevron"/arrow-point cutouts on the right side.

#### D. People Page
*   **Header:** Large panoramic photo of the team with rounded corners.
*   **Layout:** Organized by role (Director, Post-Docs, Grad Students, Undergrad Students).
*   **Member Cards:** Horizontal cards (roughly 80% container width). Left side has a square white placeholder for the profile photo; right side has Name, Title, and Bio in white text on a maroon background. Rounded corners.

#### E. Publications Page
*   **Layout:** Chronological list design.
*   **Header/Tools:** "Sorted By Year" dropdown and a search bar at the top right.
*   **List Entries:**
    *   The Year acts as a large vertical heading on the left for that group.
    *   Publication Title is bold maroon.
    *   Authors and buttons (PDF / DOI links) below title.
    *   Technical/gear icon separating the list visually.
    *   Horizontal dividers between major sections.
