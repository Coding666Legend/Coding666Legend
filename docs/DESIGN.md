# AKOS // Design Documentation & Architecture Guide

This document outlines the visual design system, color palette, SVG asset architecture, and customization workflows for the **AKOS (Aditya Khaire Security Operations)** Red Team GitHub Profile interface.

---

## 1. Visual Design Philosophy

The profile is designed as a classified **Red Team Operator Console & Intelligence Dossier**.

Key tenets:
* **Tactical Realism over Cliché**: Avoids generic hacker tropes (green matrix rain, random skulls, exaggerated claims). Replaces them with professional high-tech security operations console aesthetics.
* **Controlled Visual Hierarchy**: Uses color strictly to convey status, security classification, and domain relationships rather than arbitrary decoration.
* **GitHub Native Compatibility**: Fully standard GitHub Markdown compliant. Uses SVG vectors for resolution-independent high-contrast graphics, responsive HTML table layouts, and collapsible `<details>` blocks.
* **Honest Technical Credibility**: All claims, skills, and tools strictly align with actual operator competencies and lab environment practices.

---

## 2. Color Palette & Functional System

| Token | Hex Code | Visual Identity | Functional Role |
| :--- | :--- | :--- | :--- |
| **BACKGROUND** | `#05060A` / `#0A0C14` | Deep Cyber Dark | HUD base frame, panel backgrounds |
| **PRIMARY** | `#FF003C` | Crimson Red | Offensive action, classification, critical headers |
| **SECONDARY** | `#00F0FF` | Electric Cyan | Telemetry data, HUD reticles, primary text accents |
| **SUCCESS** | `#39FF14` | Neon Green | Verified status, online system indicators, completed tasks |
| **WARNING** | `#FFB000` | Amber / Gold | Tasks in progress, warnings, pending cert targets |
| **ACCENT** | `#A855F7` | Ultraviolet / Purple | Active Directory, specialized research, graph analytics |
| **TEXT / MUTED** | `#E6E6E6` / `#A0AAB8` | Monospace Cool Slate | Readable body typography & secondary telemetry |

---

## 3. Visual Asset Architecture

```text
assets/
├── hero-banner.svg        # Top HUD Banner: Radar reticle, status badges, operator ID
├── attack-path.svg        # Vector Attack Methodology Lifecycle Flowchart
└── headers/               # Section Header SVGs (900x50px)
    ├── dossier.svg        # 01 // OPERATOR DOSSIER
    ├── attack-path.svg    # 02 // ATTACK METHODOLOGY
    ├── arsenal.svg        # 03 // TACTICAL ARSENAL
    ├── operations.svg     # 04 // ACTIVE OPERATIONS
    ├── intelligence.svg   # 05 // FIELD INTELLIGENCE & LOGS
    ├── certs.svg          # 06 // CERTIFICATION TRAJECTORY
    ├── telemetry.svg      # 07 // SYSTEM TELEMETRY & METRICS
    └── comms.svg          # 08 // SECURE COMMS & TRANSMISSIONS
```

### SVG Technical Specifications
* **ViewBox Standard**: Header banners are `900x50`, Hero banner is `900x260`, Attack Path is `900x380`.
* **Zero External Dependencies**: Built using standard SVG paths, rects, text nodes, radial/linear gradients, and standard SVG blur filters.
* **Responsive Scaling**: Utilizes `viewBox` with `width="100%"` for automatic mobile and desktop downscaling.

---

## 4. Maintenance & Customization Workflow

### A. Updating Active Operations (Projects)
To add a new project card, edit the table under `04 // ACTIVE OPERATIONS` in `README.md`:

```html
<tr>
  <td width="50%" valign="top">
    <h4><code>OPERATION 00X // YOUR-PROJECT-NAME</code></h4>
    <p><b>OBJECTIVE:</b> Primary goal of the project.</p>
    <p><b>TECH STACK:</b> Languages/tools used.</p>
    <p><b>DESCRIPTION:</b> Brief technical description.</p>
    <p><a href="https://github.com/Coding666Legend/your-repo"><code>[ VIEW MISSION REPOSITORY ]</code></a></p>
  </td>
</tr>
```

### B. Adding Field Intelligence Logs (Writeups)
To add a writeup log under `05 // FIELD INTELLIGENCE & LOGS`:

```html
<details>
  <summary><b>[ INTEL LOG 00X ] Title of Your Writeup or Research</b></summary>
  <br/>
  <p><b>SUMMARY:</b> Executive summary of findings or attack vectors.</p>
  <p><b>KEY TAKEAWAYS:</b> Technical mitigations or critical lessons learned.</p>
</details>
```

### C. Updating Certification Trajectory
Edit the monospace table inside the code block under `06 // CERTIFICATION TRAJECTORY`:

* `[✓]` = Completed Certification / Milestone
* `[◉]` = Currently In Progress
* `[ ]` = Future Target Goal

---

## 5. Quality & Compliance Checklist

- [x] **No Fabricated Credentials**: All certs, tools, and social links match provided user data.
- [x] **GitHub Compatibility**: Tested against standard GitHub Markdown rendering rules.
- [x] **Lightweight Assets**: Clean inline SVG paths with vector optimization.
- [x] **Responsive Layout**: Adapts gracefully across desktop and mobile screen widths.
