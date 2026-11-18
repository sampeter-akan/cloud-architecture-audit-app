# T-MINUS COUNTDOWN: CLOUD ARCHITECTURE AUDIT

[![Live Deployment](https://img.shields.io/badge/Live_App-Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://cloud-architecture-audit-app.vercel.app/)
[![Architecture](https://img.shields.io/badge/Architecture-Zero--Build_SPA-F59E0B?style=for-the-badge&logo=html5&logoColor=black)](#architecture--technical-highlights)
[![Timezone Sync](https://img.shields.io/badge/Time_Sync-08:00_UTC_Global-1C2541?style=for-the-badge&logo=clockify&logoColor=white)](#global-multi-timezone-synchronization)

An executive-grade, interactive **T-Minus Mission Countdown & Desktop Lock Screen Generator** built to orchestrate the **Cloud Architecture Audit** client deliverable targeting **Wednesday, December 30, 2026 at 08:00:00 UTC**.

Designed for distributed cloud engineering and governance teams, the application combines real-time multi-timezone telemetry, a business-day backward execution schedule, URL-encoded state sharing, one-click `.ics` calendar provisioning, and a dynamic `1920x1080` desktop lock screen exporter.

---

## Live Production Deployment

* **Production URL:** [https://cloud-architecture-audit-app.vercel.app/](https://cloud-architecture-audit-app.vercel.app/)
* **Source Repository:** [https://github.com/sampeter-akan/cloud-architecture-audit-app](https://github.com/sampeter-akan/cloud-architecture-audit-app)

---

## Executive Capabilities

1. **Real-Time T-Minus & Business-Day Telemetry:**
   * Live second-by-second countdown (`Days`, `Hours`, `Minutes`, `Seconds`) synchronized to **December 30, 2026 at 08:00:00 UTC**.
   * **Active Workday Calculator:** Automatically filters out weekends (Saturday/Sunday) and year-end Christmas holiday observances (`Dec 25` and `Dec 28, 2026`) to display true remaining execution days.
2. **Global Multi-Timezone Synchronization (DST-Aware):**
   * Anchored universally at **08:00 UTC** with live conversions across key operational hubs via the browser's `Intl.DateTimeFormat` engine:
     * **UTC (Universal):** `08:00 UTC`
     * **United Kingdom (GMT / BST):** `08:00 GMT / 09:00 BST`
     * **European Union (CET / CEST):** `09:00 CET`
     * **US Pacific (PST / PDT):** `00:00 PST`
     * **US Eastern (EST / EDT):** `03:00 EST`
     * **West Africa Time (WAT):** `09:00 WAT`
3. **Interactive 11-Checkpoint Audit Roadmap:**
   * Tracks 11 concise, under-five-word milestones from **T-28** through **T-0** with automatic status indicators (`COMPLETED`, `NEXT UP`, `UPCOMING`, `OVERDUE`), live progress bar calculation, and full CRUD support for adding or editing custom checkpoints.
4. **Distraction-Free Lock Screen Mode & `1920x1080` PNG Exporter:**
   * **Lock Screen Mode (`ESC` to exit):** Hides all configuration toolbars and leaves clean `14vh` headroom at the top for desktop clocks and OS icons.
   * **HTML5 Canvas PNG Exporter:** Renders a high-resolution `1920x1080` (`16:9`) wallpaper blending the weathered wood plank backdrop (`background-img.jpg`), frosted charcoal executive card, live checkbox states, and footer watermark—ready to apply directly as a Windows/macOS lock screen.
5. **Stateless URL Sharing & Calendar Provisioning:**
   * **Shareable State URL:** Serializes checked milestones and custom edits directly into URL parameters (`?done=...#s=...`) so stakeholders see your exact real-time audit progress without requiring a backend database.
   * **Universal `.ics` Calendar Export:** Generates a multi-event `RFC 5545` iCalendar file (`Cloud-Architecture-Audit-Milestones.ics`) with `08:00 UTC` alarms for instant import into Google Calendar, Outlook, or Apple Calendar.
   * **Self-Contained HTML Exporter:** Bakes custom milestone updates directly into a downloadable `index.html` snapshot for seamless Git commits.

---

## Backward T-Minus Execution Schedule

All milestones are scheduled at **08:00 UTC** on active Monday–Friday business days (excluding December 25 & December 28 public holiday observances):

| Countdown | Scheduled Date | Milestone Deliverable | Status Focus |
| :--- | :--- | :--- | :--- |
| **T-28 Days** | Thu, Nov 19, 2026 | Define audit scope and access | Governance & IAM Onboarding |
| **T-25 Days** | Tue, Nov 24, 2026 | Stakeholder kickoff and discovery | Architecture Baseline Alignment |
| **T-21 Days** | Mon, Nov 30, 2026 | Map cloud topology and IAM | Network & Identity Inventory |
| **T-18 Days** | Thu, Dec 3, 2026 | Network and workload telemetry check | Observability & Logging Audit |
| **T-14 Days** | Wed, Dec 9, 2026 | Complete security and cost review | Posture & FinOps Optimization |
| **T-10 Days** | Tue, Dec 15, 2026 | Validate compliance and risk matrix | Control Mapping & Gap Scoring |
| **T-7 Days** | Fri, Dec 18, 2026 | Draft architecture findings report | Technical Documentation |
| **T-5 Days** | Tue, Dec 22, 2026 | Remediation roadmap walkthrough | Prioritized Action Plan |
| **T-3 Days** | Thu, Dec 24, 2026 | Internal peer review and polish | Quality Assurance Sign-Off |
| **T-1 Day** | Tue, Dec 29, 2026 | Finalize executive deck and package | Deliverable Packaging |
| **T-0 Days** | Wed, Dec 30, 2026 | Deliver final audit to client | Final Client Handover |

---

## Repository Structure

```text
cloud-architecture-audit-app/
├── index.html            # Complete single-file application (UI, telemetry engine, Canvas PNG & ICS exporters)
├── background-img.jpg    # Full-bleed weathered vertical wood plank background asset (lowercase for Linux/Vercel)
└── README.md             # Executive documentation and deployment guide
```

---

## Architecture & Technical Highlights

* **Zero-Build Single-File Architecture:** Engineered entirely within `index.html` using semantic HTML5, Tailwind CSS (CDN), and vanilla ES6+ JavaScript—requiring zero `node_modules`, bundlers, or server runtime overhead.
* **Resilient Hybrid Persistence:** Automatically synchronizes state across URL hash encoding (`#s=`), query parameters (`?done=`), and `localStorage` (`tminus_audit_state_v2`) with seamless schema migration.
* **High-Contrast Frosted Glass UI:** Pairs a textured rustic wood backdrop (`background-img.jpg`) with elevated dark charcoal/espresso glassmorphism (`rgba(20, 22, 26, 0.80)`) and warm executive amber accents (`#F59E0B`).

---

## Local Development & CI/CD Deployment

### Run Locally
Because the HTML5 Canvas PNG exporter reads `./background-img.jpg`, serve the directory over a local HTTP server to avoid browser `file://` CORS restrictions:

```powershell
# Using Python 3
python -m http.server 8080
# Open http://localhost:8080 in your browser
```

### Continuous Deployment (GitHub → Vercel)
Any push to the `main` branch automatically triggers a zero-config production build on Vercel:

```powershell
git add README.md
git commit -m "docs: add executive README.md documentation"
git push origin main
```

---

## Copyright & Trademark

© 2026 **Samuel Peter™** • Cloud Architecture Audit Countdown. All Rights Reserved.