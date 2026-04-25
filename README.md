Download figure-descriptions-skill-package.zip file from Dropbox at https://tinyurl.com/3b9zyx3b

Figure Description Skills Package
A skill package for Claude (likely also gpt 5.5) that handles figure descriptions in study guides — including circuit diagrams, hydraulic/pneumatic schematics, and practice problem images — with a focus on accessibility for blind and visually impaired students.

Overview
This package bundles four integrated skills intended to be used together. They cover the full workflow: writing descriptions from images, inserting them into Word documents, handling domain-specific schematic types, and verifying circuit details before describing them.
Skills Included

Skill 1 — Figure Descriptions for Study Guides
Core content and formatting rules for writing figure descriptions read aloud by screen readers. Covers:

Label format and length conventions
What to include and exclude based on the paired student instruction
How to examine images before writing
Structure and grouping rules for multi-element figures
Positional language rules

Skill 2 — Figure Description Docx Workflow
Step-by-step workflow for inserting descriptions into .docx study guide files. Covers:

Inventorying documents and images
Determining correct image order from document XML (not filenames)
Inserting description paragraphs via unpack → edit XML → repack
XML structure for bold label + normal description text
Known issues: pre-existing validation errors, grid-layout numbering, image rendering problems, ambiguous value verification, paired images

Skill 3 — Hydraulic and Pneumatic Schematics
Supplemental rules for hydraulic and pneumatic circuit images. Overrides Skill 1 where they conflict. Covers:

Identifying which instruction is paired with an image
What to withhold vs. include when the student is asked to reason about a component
Tracing full flow paths and describing connection topology
Describing complete circuits, not just isolated symbols

Skill 4 — Circuit Analysis
Verification workflow for electronic circuits, amplifiers, and components. Covers:

Searching for schematics before describing topology
Fetching datasheets before stating component specs
Common failure modes and how to avoid them
Output impedance and damping factor analysis for transformer-coupled push-pull stages
Power analysis under voltage and current constraints
Cascode behavior in transformer-coupled stages
Feedback topology distinctions (local vs. global)
Stability compensation for multi-transformer feedback loops
Push-pull center tap identification from turns counts
Source quality hierarchy for schematics and datasheets

Usage
This package is a single SKILL.md file containing all four skills. Load it into a Claude (likely also compatible with gpt 5.5) session before beginning any figure description task. Read all sections relevant to your task before proceeding.
Trigger conditions:

Writing figure descriptions or alt text for study guides
Inserting descriptions into Word documents
Working with electronic circuit schematics
Working with hydraulic or pneumatic circuit schematics
Amplifier topology analysis
Transistor or transformer circuit design and verification

Dependencies
Skill 2 (Docx Workflow) also requires the docx skill for unpack/repack mechanics.

File Structure
figure-description-skills-package/
└── SKILL.md

Download figure-descriptions-skill-package.zip file from Dropbox at https://tinyurl.com/3b9zyx3b
