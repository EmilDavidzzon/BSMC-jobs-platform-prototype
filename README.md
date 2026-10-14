# Venture Studio 1st prototype

First prototype of the **International Student Jobs Platform**, a student-run
project (Milan, autumn 2026).

> Status: clickable front-end prototype ("Gigomy"). All jobs, companies and
> numbers in it are simulated; nothing is stored and there is no backend.

## The prototype

[`index.html`](index.html) is a clickable front-end blueprint of the platform,
branded **Gigomy**. It is one self-contained file: plain HTML, CSS and
JavaScript, with no frameworks, no build step and no backend. Everything is
inline except two Google Fonts (Bricolage Grotesque and Instrument Sans).

**How to open it**

- Online, via GitHub Pages: https://emildavidzzon.github.io/bsmc-jobs-platform-prototype/
- Locally: download `index.html` and open it in any browser.

All companies, jobs, applicant numbers, profiles and map locations are
**simulated**. Nothing is saved, nothing is sent anywhere, and no personal data
is collected.

### Colour palette

Cool greys with two accents. About 90% of every screen is grey and white, so
the accents stand out.

| Colour | Hex | Used for |
| --- | --- | --- |
| Orchid | `#A67CBA` | Primary buttons and verified badges only. Always dark text on it, never white. |
| Gold | `#FFD700` | One highlight per screen: "New", pending (e.g. "In review", the admin queue count) and the logo dot. Never as text on white. |
| Graphite | `#1D1B2E` | Text, top bar, footer, dark panels |
| Slate | `#5F6478` | Secondary info, captions, map lines and charts |
| Mist | `#DCDDE8` | Borders, dividers |
| Cloud | `#F6F6FA` | Page sections, tags |
| White | `#FFFFFF` | Main background |
| Error | `#B42318` | Form errors only |

Links are graphite text with an orchid underline, because orchid text on white
is too faint to read. The colours are CSS variables at the top of `index.html`
(`--graphite`, `--slate`, `--mist`, `--cloud`, `--orchid`, `--gold`,
`--error`). No other colours are used anywhere, including the map: form
inputs use slate borders, and shadows are graphite with transparency.

### Navigation

A "Prototype" bar at the top of every page jumps straight to any screen.
Pages are switched with the URL hash, so every screen has a shareable link:

| Link | Screen |
| --- | --- |
| `#home` | Landing page |
| `#jobs` | Browse jobs |
| `#jobs/day`, `#jobs/tutoring`, `#jobs/project`, `#jobs/internship`, `#jobs/parttime`, `#jobs/high`, `#jobs/remote` | Browse jobs, pre-filtered to one category |
| `#job` | Job detail (sample listing) |
| `#signup` | Student sign-up |
| `#company` | Company dashboard |
| `#admin` | Admin dashboard |
| `#about` | About the project and the team |

### 1. Home (`#home`)

- **Hero**: "Internships and part-time work in Milan — in English", with
  "Create your student profile" and "I'm hiring — post a job" buttons and three
  promises: verified student profiles, always free for students, and apply directly
  to employers.
- **Interactive map of Milan** (inline SVG):
  - 17 company pins covering 20 on-site and hybrid roles. The 4 remote
    roles are linked separately.
  - Each pin shows the company initial, the number of people applying and a
    mini bar chart of applications over the last 7 days.
  - Hovering over or focusing a pin opens a tooltip listing each open role
    with its pay, category, date posted, applicant count and a 7-day sparkline.
  - Clicking a pin opens the job detail page.
  - You can drag to pan, use the + / − / reset buttons, double-click to zoom,
    or click the map once and then scroll to zoom.
  - A "Open Milan in Google Maps" link sits below the map.
- **Audience strip**: Bachelor's, Master's and exchange students; small
  internships; part-time roles; Milan businesses and startups.
- **Browse by category**: six tiles (Day jobs, Tutoring, Week-long projects,
  High-paying, Internships, Remote-friendly) showing live counts. Each tile
  opens the job board pre-filtered.
- **How it works**: three steps for students (verify, build a profile, browse
  and reach out) and three for companies (create a profile, post a role, hear
  from verified students).
- **Principles**: Student-first, Trust-based, English-friendly and Non-profit.
- **Latest opportunities**: three featured job cards.
- **About this project**: a teaser with the semester targets (100 students,
  10 partner companies, €0 cost to students).
- **Call to action**: "Your next shift is in English", inviting students and
  employers to join before launch on 18 December.
- **Footer**: links to the privacy notice, terms, feedback and contact.

### 2. Browse jobs (`#jobs`)

- **Search** by role, company or category, filtering as you type.
- **Category shortcuts**: the same six tiles as on the home page.
- **Filters** (the panel stays visible on wide screens):
  - Category: Day jobs, Tutoring, Week-long projects, Internships, Part-time,
    each with a count.
  - Minimum pay slider from €0 to €30+/h. Day rates, project fees and monthly
    pay are converted to an hourly estimate so they can be compared.
  - When: Weekdays, Evenings, Weekends, Flexible.
  - Work mode: On-site, Hybrid, Remote.
  - Language: "No Italian required".
  - Sort: Best match, Highest pay, Newest.
  - A Reset button clears everything.
- **Browse view** (the default):
  - "Recommended for you": the top six matches, each with a match score and a
    reason such as "Fits your weekend availability", based on a sample profile
    (weekends, evenings, English).
  - One horizontal row per category (Day jobs, Tutoring, Week-long projects,
    High-paying at €18/h or more, Internships, Remote-friendly), each with a
    "See all" button.
- **Results view**: shown once you search or pick a category. It has a title,
  a result count, chips for the active filters, a "Clear all" button, an empty
  state and "Back to browsing".
- **Job cards** show the company initial, title, a verified-employer shield,
  category, duration, area, a "Basic Italian" tag where Italian is needed, pay
  and schedule.

### 3. Job detail (`#job`)

A sample listing: **Weekend barista at Nebbia Coffee Bar**.

- Tags (Part-time, English only), a verified-employer badge, and the key facts:
  pay €11/h, Sat & Sun 8:00–14:00, Porta Venezia, starting in November.
- Sections: About the role, What you'll do, Good to know. "Good to know" says
  that the contract and pay are agreed directly with the employer.
- **How to apply** panel: "Apply on employer's site", "Email the employer" and
  "Save for later". Applications go to the employer, not through the platform.
- An employer card ("Employer reviewed by the Gigomy team") linking to the
  company profile, and a **Report this listing** link.

### 4. Student sign-up (`#signup`)

A three-step progress bar (Verify student email → Build your profile → Start
browsing), shown at step 2.

1. **Student email**: shows a verified student address. Only verified student
   addresses can join, confirmed with a 6-digit code, and the student email
   is never shown to employers.
2. **About you**: full name, contact email shown to employers, programme, year
   of study (1st to 3rd year, Master's, Exchange student), languages with level
   and an "Add language" button, availability (Weekends, Evenings, Weekday
   mornings, Remote), a short intro, and an optional CV upload (PDF up to 5 MB).
3. **Privacy**: a required consent to the privacy notice, an optional email
   alert for matching roles, and a note that you can download or delete your
   data at any time.

There are "Save draft" and "Finish and browse jobs" buttons. A side panel
previews **what employers see**: name, programme, a verified-student badge,
languages, availability and CV status. The profile is visible only to reviewed
employers, never publicly.

### 5. Company dashboard (`#company`)

Shown as the sample employer **Nebbia Coffee Bar**.

- **Company profile** card with a "Reviewed employer" badge, sector,
  neighbourhood, website, description and "Edit profile".
- **Post an opportunity** form:
  - Role title, type of work (Part-time, Day job, Tutoring, Week-long project,
    Internship), location, pay and schedule.
  - Language requirement: English only, or English + basic Italian.
  - A description.
  - How students should apply: a link to the company's application page or by
    email. A note says the platform doesn't handle applications, contracts or
    payments.
  - "Preview" and "Submit for review". Submitting switches the button to
    "Submitted — in review", and listings are reviewed within one working day.
- **Your listings**, with status chips: Live, In review and Draft.
- A **Help us improve** feedback prompt.

### 6. Admin dashboard (`#admin`)

- A side navigation with Overview, Review queue (with a live count), Students,
  Companies, Reports and Feedback.
- **Progress against the semester goal**: 64 / 100 verified students, 7 / 10
  reviewed companies and 18 live listings (with apply clicks tracked per
  listing).
- A **review queue** that works: Approve or Reject removes the item and updates
  the counts, with an "All caught up" state when it's empty. It holds sample
  items of each kind: a listing, a company registration, and a student who
  signed up with an unrecognised student email and needs a manual check.
- **Reported listings** (for example "Pay unclear" or "Italian required") and
  **latest feedback** from students and employers.

### 7. About and team (`#about`)

- **Mission**: making the job market in Milan more accessible for
  English-speaking international students.
- **Our motives**: the language barrier, scattered opportunities, small
  businesses that can't reach students, and learning by building.
- **Four principles**: Student-first, Trust-based, Discovery only and
  Non-profit.
- A **prototype disclaimer**: everything is simulated, nothing is connected,
  no personal data is collected, and Gigomy is an independent student
  initiative.
- **Meet the team**: member cards with initials avatars and a member count.

### Sample data

| | |
| --- | --- |
| Listings | 24: 5 day jobs, 5 tutoring, 5 week-long projects, 4 internships, 5 part-time |
| Companies | 19 fictional employers (cafés, startups, studios, families) |
| Work mode | 13 on-site, 7 hybrid, 4 remote |
| Language | 22 English only, 2 English + basic Italian |
| Pay | €9.50 to €30 per hour (estimated); 6 roles are "high-paying" (€18/h or more) |
| Applicants | 611 simulated applicants across all listings |

### What is interactive and what is a mock-up

**Works in the prototype:** page navigation and deep links, the map (pan,
zoom, pins, tooltips), category counts, search, all filters and sorting,
recommendations, the category rows and results view, the admin approve/reject
queue, the "Submit for review" button, and scroll animations (which respect
the reduced-motion setting).

**Visual only, not wired up yet:**

- Every job card and map pin opens the same barista listing.
- Apply, email, save, report, sign in, CV upload, add language, save draft,
  preview and edit buttons do nothing.
- Sign-up form fields aren't saved, and email verification is shown as already
  complete.
- The admin sections other than Overview have no content of their own.
- Footer links (privacy notice, terms, feedback, contact) go back to the home
  page.

### Editing the prototype

All the content lives in the `<script>` at the bottom of `index.html`:

| What | Where in the script |
| --- | --- |
| Job listings | `JOBS` array (title, company, category, area, mode, schedule, pay, hourly `rate`, match score) |
| High-paying threshold | `HIGH_PAY` (currently €18/h) |
| Applicant counts per listing | `APPL` |
| Map pin positions per company | `POS` (a company not listed here is counted as remote) |
| Admin review queue | `queue` |
| Team members | `TEAM` |

Colours (see [Colour palette](#colour-palette)) and fonts are CSS variables in
`:root` at the top of the file. The map
is a large inline SVG (around 430 KB) inside `#map-stage`, which makes up most
of the file size.

## Semester goal

Launch a working platform with **100+ registered students and 10+ registered
companies by 18 December 2026**.

## The problem

International and English-speaking university students in Milan often struggle
to find flexible, student-friendly work, because many opportunities require
Italian or are scattered across informal channels.

## The solution

A simple platform where students create verified profiles and companies publish
English-friendly opportunities. Discovery happens on the platform; applications,
contracts and payments stay outside it.

## Product principles

- **Student-first**: free, low-friction access and flexible opportunities that
  fit around university life.
- **Trust-based**: verified student status, clear employer profiles and
  transparent job information.
- **Simple MVP**: prioritise discovery, profiles and external contact over
  complex integrations.
- **Non-profit first**: build utility and adoption before any monetisation
  discussion.

## Core MVP features

| Students | Companies | Platform |
| --- | --- | --- |
| Sign-up and profile creation | Company registration and profile | Admin dashboard for moderation |
| University-student verification | Job / gig posting | Basic usage tracking and feedback collection |
| Job browsing with basic filters | | |
| External application or contact flow | | |

## Roadmap

| Dates | Phase | Focus | Owners |
| --- | --- | --- | --- |
| 5-31 Oct | Research + V1 + legal clearance | Validate student interest, narrow the first employer segments, define acquisition ideas for both sides. Build the first usable version in parallel. Close legal, privacy and verification questions. | Research, Product, Partnerships |
| 1-14 Nov | Test + marketing activation | Focused 1-2 week test with a small user group, fix the main friction points, launch the first student and employer acquisition initiatives. | Product, Growth, Partnerships |
| 15 Nov-10 Dec | Scale + iterate | Push student and company acquisition in parallel; keep improving the platform from real usage. | All workstreams |
| 11-18 Dec | Final push + delivery | Close remaining product issues, intensify outreach, deliver a stable platform that hits the semester goal. | All workstreams |

## Open questions (to close by 31 October)

- **Access scope**: international students only, or open from day one? If
  broader, define a simple eligibility filter.
- **Student verification**: university email domains / patterns plus email
  verification, unless a stronger integration is actually needed.
- **Legal status**: confirm whether registration or other formal steps are
  required, and complete them before launch.
- **Data & GDPR**: define data collected, privacy notice, consent, retention
  and controller / processor responsibilities.
- **External support**: identify a lawyer, university office, alumnus or
  trusted professional to validate legal and privacy choices.

## Working model

- **Weekly studio session**: about 2 hours together each week, ideally on a
  weekend, to review progress, unblock decisions and work on the project.
- **Flexible individual work**: outside the session, contribute individually or
  in small groups according to availability. Team leads remain available for
  support.

## Definition of success

Validated demand + working product + real users + real companies + compliant
operating model.

---

Source: *International Student Jobs Platform, project brief, October 2026*
(internal working document).
