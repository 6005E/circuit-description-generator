---
name: figure-description-skills-package
description: "Use this skill package for any task involving figure descriptions in study guides, including electronic circuit diagrams, hydraulic/pneumatic schematics, and practice problem images. Covers writing descriptions for blind or visually impaired students, inserting descriptions into .docx files, and analyzing electronic circuits. Triggers include: writing figure descriptions or alt text for study guides, inserting descriptions into Word documents, working with circuit schematics (electronic, hydraulic, or pneumatic), amplifier analysis, and transistor/transformer circuit design. This package contains four integrated skills: figure-descriptions (content and formatting rules), figure-description-docx (Word document workflow), figure-descriptions-hydraulic-pneumatic (hydraulic/pneumatic circuit rules), and circuit-analysis (electronic circuit verification and analysis)."
---

# Figure Description Skills Package

This package contains four skills intended to be used together. Read all sections relevant to your task before proceeding.

---

# SKILL 1: Figure Descriptions for Study Guides

Descriptions are read aloud by screen readers for blind or visually impaired students. The student must be able to complete all work without seeing the image.

## Format

- Label: **Figure 1.**, **Figure 2.**, etc. — bold, in sequence throughout the document
- Label and description are on the same line, in the same paragraph
- Label is bold; description text is not
- Length: 1–2 sentences
- Declarative sentences only — no imperative verbs (avoid: determine, identify, calculate, find)

## Content Rules

**Include:**
- All given values shown in the image
- Component values and frequencies for circuit diagrams
- Convey functional state of all components and include all values and labels visible in the image when the student is asked to describe or explain behavior

**Exclude:**
- Anything the student is asked to determine, explain, or describe — that is their task, not the description's job
- Repetition or paraphrase of surrounding instructions

**Before writing:** Identify the verb in the surrounding student instruction. It determines what information the description must provide:
- "describe the operation" → convey functional state of all components; if the instruction asks the student to describe the operation of the entire circuit, withhold how the components interact to produce the circuit's function — describe topology and component states only. The interaction is the student's answer.
- "calculate" / "determine" → provide all given values
- "compare and contrast" → explicitly convey differences between diagrams

**If the image has no visible content:** Write: `No visible content.`

**If the image is a video screenshot:** Describe only the mathematical or technical content — do not mention that it is a screenshot.

## Examining Images

Before writing a description, examine each component and connection in the image explicitly and in order. 

When pages contain multiple small exercise graphs where precise grid values must be read, use 200 DPI or higher when rasterizing. At lower resolutions, fine grid detail on small embedded graphs is unreliable and can produce misreads of asymptote positions, branch extrema, and axis values.

When precise grid values are required — asymptote positions, branch extrema, intercepts — crop and re-examine the individual graph before writing the description. Do not describe small graphs embedded in a full page without zooming in first.

Do not infer state or topology from visual cues like color, position, or familiar patterns — verify each one directly. For circuit diagrams this means tracing every current path. For any image with multiple elements, account for each one before writing.

Do not apply system-level descriptors (e.g. "three-phase," "wye-connected," "delta-connected," "series circuit," "parallel circuit") unless the image explicitly shows the interconnection that justifies the label. The fact that components have values or labels consistent with a known configuration is not sufficient — the connection itself must be visible.

After drafting a description, verify that every visible element in the image — including labels, annotations, symbols, and component details such as dot positions — is accounted for by name. A generic phrase like "phase dots shown" does not suffice if the dot positions are visible and functionally meaningful; state which terminals are dotted.

Describe only what is fully visible in the graph. Do not draw conclusions about any feature — amplitude, period, midline trend, or behavior — from a partial cycle, a clipped curve, or a region where the graph exits the frame. If a feature cannot be confirmed from complete, visible data, do not state it

## Structure and Grouping

- When elements belong together (e.g. an exponent, a symbol, and a name all describing the same prefix), make those relationships explicit. Do not list elements separately.
- Present information in natural reading order: column-based layouts go top-to-bottom per column; row-based layouts go left-to-right.
- For multiple practice problems in one image: number each (1), (2), etc. State shared operations or structures once upfront; note exceptions individually.
- For multiple circuit diagrams in one figure: describe shared elements once, then note what differs in each. Use neutral ordinal language: "the first", "the second", "one", "the other" — not "the left" or "the right".

## Positional Language

- Do not describe left/right/middle positions of parallel components — their order is interchangeable.
- Do not use directional language (e.g. "far right", "top left") unless functionally necessary.
- Positional language is appropriate when it identifies a functionally distinct element (e.g. which branch contains an ammeter, a short, or an open circuit).

## Example Descriptions

**Figure 1.** A 120V, 60Hz AC source connected to two parallel branches: a 500Ω resistor and a 10μF capacitor.

**Figure 2.** A 120V, 60Hz AC source connected to three parallel branches: a 500Ω resistor, a 10μF capacitor, and a 950mH inductor.

**Figure 3.** Two parallel AC circuits, each with a 120V/60Hz source, 500Ω resistor, 10μF capacitor, and 950mH inductor. One circuit has ammeters on the source line and on the resistor branch. The other has ammeters on the source line and on the inductor branch.

**Figure 4.** Four polar format complex number problems, each requiring Ā·B̄ and Ā/B̄: (1) Ā=6.6−74.1°, B̄=1.3−157.4°; (2) Ā=8.1−108.7°, B̄=5.0−−56.3°; (3) Ā=10.1−107.9°, B̄=8.1−119.4°; (4) Ā=6.0−−16.3°, B̄=10.5−48.1°.

**Figure 5.** Five series circuit problems: (1) R=180Ω, C=24μF, f=50Hz; (2) R=300Ω, L=430mH, f=80Hz; (3) R=470Ω, L=67mH, C=0.12μF, f=1.5kHz; (4) R=220Ω, Ri=10Ω, L=390mH, f=60Hz; (5) R=750Ω, C1=3.9μF, L=180mH, C2=4.3μF, f=200Hz.

---

# SKILL 2: Figure Description Docx Workflow

This skill covers the figure-description-specific steps for inserting descriptions into study guide .docx files. Also read the **docx** skill (`/mnt/skills/public/docx/SKILL.md`) for unpack/edit XML/repack mechanics.

## Session Checklist

- [ ] Read figure-descriptions skill (content/formatting rules) — Skill 1 above
- [ ] Read docx skill (unpack/repack mechanics)
- [ ] Inventory all documents before writing any descriptions
- [ ] Verify image order from document XML for each file
- [ ] View all images before writing any descriptions
- [ ] Write all descriptions (following figure-descriptions skill)
- [ ] Insert into documents via unpack → edit XML → repack
- [ ] Validate outputs (pre-existing pgMar error can be ignored — see Known Issues)
- [ ] Present files to user

## 1. Inventory

When a zip arrives:
```bash
unzip -l archive.zip
# Extract to working directory, then for each .docx:
unzip -l file.docx | grep word/media/
```

## 2. Determine Image Order

**Critical:** image filenames (image1.png, image2.png, etc.) do NOT match document order. Always verify order from the document XML:

```bash
unzip -p file.docx word/document.xml | grep -o 'image[0-9]*\.\(png\|jpg\)' | uniq
```

Use this order — not the filenames — when numbering figures.

## 3. Extract and View All Images

```bash
unzip -p file.docx word/media/image1.png > image1.png
```

View **all** images before writing any descriptions. Do not write descriptions one at a time as you go.

## 4. Check Surrounding Text

Check what text surrounds each image before writing or placing a description. Use pandoc to read document structure:
```bash
pandoc file.docx -t markdown
```

**Only the instruction immediately preceding the image is paired with it.** Instructions further above are separate questions and do not relate to that image.

Per the guidelines: if associated data (e.g. a dimensions list or given values) follows the image in the document, place the figure description **after** that data, not immediately after the image.

If the same image appears in multiple documents, write the same description each time.

## 5. Insert Descriptions

Use the unpack → edit XML → repack approach from the docx skill.

The description paragraph is inserted immediately after the closing `</w:p>` of the paragraph containing the image. Find the image paragraph by searching for `name="image1.png"` (or whichever image) in the XML, then find its closing `</w:p>`.

### Description Paragraph XML Structure

Bold label and normal description text are separate `<w:r>` runs in the same `<w:p>`. Match the font and size of the surrounding document (typically Calibri, sz=22).

```xml
<w:p>
  <w:r>
    <w:rPr>
      <w:rFonts w:ascii="Calibri" w:hAnsi="Calibri"/>
      <w:b w:val="1"/>
      <w:sz w:val="22"/>
      <w:szCs w:val="22"/>
    </w:rPr>
    <w:t xml:space="preserve">Figure 1. </w:t>
  </w:r>
  <w:r>
    <w:rPr>
      <w:rFonts w:ascii="Calibri" w:hAnsi="Calibri"/>
      <w:b w:val="0"/>
      <w:sz w:val="22"/>
      <w:szCs w:val="22"/>
    </w:rPr>
    <w:t>A 120V, 60Hz AC source connected to two parallel branches: a 500Ω resistor and a 10μF capacitor.</w:t>
  </w:r>
</w:p>
```

Note `xml:space="preserve"` on the bold run's `<w:t>` to preserve the trailing space after the label.

---

## Known Issues

### Pre-existing Validation Error

All documents in this project fail validation with:

```
Element 'w:pgMar': The attribute 'w:gutter' is required but missing.
```

This error is pre-existing in the original files — confirmed by running the validator against originals before any edits. It can be ignored. Documents open and function correctly in Word despite this error.

### Grid-Layout Practice Problems

For groups of practice problems displayed in a grid, number figures in reading order: left to right, top to bottom.

### Image Rendering Problems

Some images fail to render or render black due to colormap or alpha channel issues. If an image does not display correctly after extraction, composite onto a white background before converting:

```python
from PIL import Image
img = Image.open('image.png').convert('RGBA')
bg = Image.new('RGBA', img.size, (255, 255, 255, 255))
bg.paste(img, mask=img.split()[3])
bg.convert('RGB').save('image.jpg', format='JPEG', quality=95)
```

This handles both 8-bit colormap PNGs and RGBA images where the alpha channel causes black rendering. Apply to any image that renders as solid black or blank.

### Verifying Ambiguous Values

When a value in an image is small or unclear, crop and upscale the relevant area before writing the description:

```python
from PIL import Image
img = Image.open('image.png')
w, h = img.size
crop = img.crop((int(w*0.4), 0, int(w*0.6), h))  # adjust bounds to target area
bg = Image.new('RGBA', crop.size, (255, 255, 255, 255))
bg.paste(crop.convert('RGBA'), mask=crop.convert('RGBA').split()[3])
bg.convert('RGB').resize((crop.width*4, crop.height*4), Image.LANCZOS).save('crop_4x.jpg', format='JPEG', quality=95)
```

Do not write a description for a value you cannot read. Flag it for review.

### Paired Images

When two consecutive images in the document belong to the same surrounding instruction, treat them as a single figure with one description covering both circuits.

---

# SKILL 3: Figure Descriptions — Hydraulic and Pneumatic Schematics

Use this skill alongside Skill 1 (figure-descriptions). The rules here supplement and, where they conflict, override Skill 1.

## Identifying the Paired Instruction

Only the instruction immediately preceding the image is paired with it. Instructions further above are separate questions and do not relate to that image.

Before writing, identify two things from the paired instruction:
1. The specific component or detail the student is asked to address
2. What the student is asked to produce (their answer)

Withhold only what the student is asked to produce. Do not withhold inputs to their reasoning — if the orientation, value, or state of a component is what the student reasons *from*, include it even when the question is about that component.

Example: "Describe how the orientation of the check valve bypass influences this actuator's action." → The student must determine the *influence*. The *orientation* is an input to their reasoning and must be included in the description.

Do not suppress other visible circuit details that are not the focus of the paired instruction.

## Examining Images

Describe the full circuit shown — not just a valve symbol or component in isolation. If the circuit includes a pump, actuator, valves, and connecting lines, all of those are part of the image and must be described.

Trace every flow path and describe how each major component connects to the others: which ports are supplied, where return lines go, and how the components relate functionally. Connection topology is essential information the student needs to visualize the circuit.

Before writing a description for any hydraulic or pneumatic circuit image, answer these questions explicitly:

- How many separate circuits are shown?
- What is the complete list of components present — pump, relief valve, directional control valves, actuators, and any other valves?
- Are there any labels or annotations on the image?
- Trace every flow path: where does flow originate, what does it pass through, and where does it return?

## Example Description

**Figure 6.** A hydraulic circuit with a pump, a pressure reducing valve with a check valve bypass oriented to allow reverse flow from the outlet port back to the inlet port, and a hydraulic cylinder connected to the valve outlet at the cap end, with the rod end returning to tank.

---

# SKILL 4: Circuit Analysis

## Core Philosophy

**Never describe a circuit, state a component spec, or make a topology claim from memory alone.** Training data frequently garbles specific real-world details even when underlying theory is correct. A confident wrong answer is worse than a hedged correct one.

The errors most likely to occur are not analytical — they are factual recall failures about specific components, circuit revisions, feedback paths, and transformer configurations.

---

## Verification Workflow

### For any named amplifier or circuit:
1. **Search first** — find the actual schematic before describing topology
   - Query: `[amp name] schematic` or `[amp name] circuit diagram`
   - Look for service manuals, repair forums (Antique Radio Forums, TalkBass, The Gear Page, DIYAudio, SSGuitar), and manufacturer docs
2. **Identify revision** — many circuits changed over production runs; flag if multiple versions exist
3. **Confirm key topology questions** before stating them:
   - IC or fully discrete?
   - NPN or PNP (or mixed)?
   - Transformer-coupled or direct-coupled output?
   - Push-pull or single-ended?
   - Supply polarity (positive or negative rail)?
   - How many transformers? (driver + output is common in transistor radio topology)
   - Feedback topology — local only, or global enclosing output transformer?
4. **Then describe** the signal path with verified information

### For component specs:
1. **Search the datasheet** — never recall specs from memory
   - Query: `[part number] datasheet` or `[part number] specs`
   - Prefer manufacturer datasheets (ON Semi, ST, Vishay, Texas Instruments, etc.) over aggregator sites
2. **Flag ambiguity** — some part numbers have conflicting versions across manufacturers
3. **Note missing parameters** — Early voltage (V_A) and h_oe are frequently absent from power transistor datasheets; flag this explicitly rather than estimating silently
4. **Report the complement** — always mention the NPN/PNP complement part if relevant

---

## Common Failure Modes — Verified Against Real Circuits

| Wrong assumption | Why it happens | Correct approach |
|---|---|---|
| "Uses an LM386 IC" | LM386 common in battery amps | Verify — many amps use fully discrete output stages |
| "NPN output transistors" | NPN silicon more common today | Check polarity explicitly; transistor-radio derived circuits often use PNP even in silicon versions |
| "Single feedback path" | Local feedback is most visible | Search specifically for global feedback — secondary-to-input loops are easy to miss |
| "No driver transformer" | Output transformer is more prominent | Transistor-radio topology uses TWO transformers; driver transformer fundamentally changes output impedance analysis |
| Stating h_FE, V_A, h_oe from memory | Values vary by manufacturer/grade | Always fetch datasheet; flag when V_A is absent |
| Assuming transformer impedance from DC resistance | DC resistance ≠ AC impedance | Back-calculate from known power/voltage/load specs |
| Treating local and global feedback as equivalent | Both reduce distortion | Only global feedback enclosing output transformer reduces output impedance and improves damping factor |
| Assuming push-pull center tap is always geometric midpoint | Seems logical | Derive from actual turns counts; true center tap requires equal turns each side — verify from specs |

---

## Output Impedance Analysis — Transformer-Coupled Push-Pull

### Step 1: Identify ALL impedance-modifying elements

Before calculating r_o, identify every element in the signal path that modifies effective output impedance:

- **Driver transformer secondary resistance** — appears in series with base; multiplies r_o via (1 + g_m × R_s)
- **Emitter resistor** — modifies operating point and g_m
- **Feedback paths** — global feedback divides output impedance by loop gain (1 + Aβ)
- **Both transformers** — driver AND output transformer must be included

**Critical:** Omitting the driver transformer secondary resistance from r_o_effective calculation will dramatically underestimate output impedance modification. The driver transformer secondary resistance effectively cascodes the output transistor.

### Step 2: Calculate r_o_effective

**r_o = V_A / I_C** (requires Early voltage from datasheet — often absent for power transistors)

If V_A is absent, use output curve slope: **r_o = ΔV_CE / ΔI_C** at constant I_B

With driver transformer secondary resistance R_s in base circuit:

**g_m = I_C / V_T** (V_T = 26mV at room temperature)

**r_o_effective = r_o × (1 + g_m × R_s)**

This is typically 10–50× higher than r_o alone — often 5kΩ–20kΩ for typical audio power transistors in this topology.

### Step 3: Calculate Z_source

**Z_source = r_o_effective || R_primary_half**

When r_o_effective >> R_primary_half (which is typical with driver transformer present):

**Z_source ≈ R_primary_half**

### Step 4: Refer to secondary

**N² = R_primary_half / R_speaker**

**Z_out = Z_source / N² = (r_o_effective || R_primary_half) / (R_primary_half / R_speaker)**

When r_o_effective >> R_primary_half this simplifies to:

**Z_out ≈ R_primary_half / N² = R_speaker**

**This means open-loop DF ≈ 1.0 in transformer-coupled push-pull stages with a driver transformer present** — regardless of output transformer impedance. This is a mathematical identity, not a coincidence.

### Step 5: Apply feedback correction

**Z_out_closed = Z_out_open / (1 + Aβ)**

**DF_closed = R_speaker / Z_out_closed = DF_open × (1 + Aβ)**

Typical loop gain for transistor-radio derived circuits: **(1 + Aβ) = 5–11**

This gives practical closed-loop DF of **5–11** — the only way to significantly exceed DF = 1 in this topology.

---

## Power Analysis — Transformer-Coupled Push-Pull

### Basic formula

**P_max = V_usable² / (2 × R_primary_half)**

Where **V_usable = V_supply - V_CE(sat)**

### Both constraints must be applied simultaneously

Current limit: **I_C_peak = V_usable / R_primary_half** (voltage-limited region)

When I_C_peak exceeds I_C_max, circuit is current-limited:

**R_crossover = V_usable / I_C_max**

- Above R_crossover: voltage-limited, P = V_usable² / (2 × R_primary_half)
- Below R_crossover: current-limited, P = ½ × I_C_max² × R_primary_half

Maximum power occurs exactly at R_crossover:

**P_max_absolute = ½ × V_usable × I_C_max**

### Effect of driver transformer step-down ratio n:1

**R_effective = R_primary_half / n²**

**I_C_peak = V_usable × n² / R_primary_half** (× n² because lower impedance demands more current)

**n_max = √(I_C_max × R_primary_half / V_usable)**

### Back-calculating transformer impedance from known power/voltage

When actual measured impedance is unavailable, derive from specs:

**R_primary_half = V_usable² / (2 × P_rated)**

This is more reliable than estimating from DC winding resistance.

---

## Cascode in Transformer-Coupled Stages

A cascode raises r_o_effective by approximately h_FE but this produces a **counterintuitive result** in transformer-coupled stages:

When r_o_effective >> R_primary_half:

**Z_out ≈ R_primary_half / N² = R_speaker → DF = 1.0**

The turns ratio cancels the high r_o exactly. **Cascoding provides no damping factor benefit in transformer-coupled push-pull stages** and actually degrades DF compared to a well-designed common-emitter stage at high primary impedances where r_o previously helped.

The driver transformer secondary resistance already effectively cascodes the output transistors — adding explicit cascode transistors is redundant in this topology.

---

## Feedback Topology — Critical Distinctions

**Local feedback** (base/emitter of input stage only):
- Stabilizes gain
- Reduces input stage distortion
- Does NOT reduce output impedance
- Does NOT improve damping factor

**Global feedback** (secondary winding back to input):
- Reduces output impedance by (1 + Aβ)
- Improves damping factor by (1 + Aβ)
- Requires stability compensation with multiple transformers in loop

**Multiple feedback paths** (as in Pignose 7-100):
- Speaker tap on primary → output transistor bases
- Secondary → driver stage input
- Both paths contribute to loop gain
- Must verify all paths exist before concluding feedback topology

**Never assume local feedback = no global feedback.** Search specifically for secondary-to-input connections.

---

## Stability in Multi-Transformer Feedback Loops

With two transformers in the feedback loop, each contributes up to -90° phase shift at high frequencies. Total possible phase shift = -180°, placing the system on the oscillation boundary if loop gain > 1 at that frequency.

### Compensation

**Dominant pole compensation** — one capacitor across feedback resistor:

**f_comp = 1 / (2π × R_feedback × C_comp)**

Place f_comp at least one decade below estimated transformer high-frequency poles (~50kHz for small audio transformers):

**f_comp = 5kHz → C_comp = 1 / (2π × R_feedback × 5000)**

For R_feedback = 10kΩ: **C_comp ≈ 3.3nF**

**Tradeoff:** loop gain rolls off above f_comp — DF improvement only applies below compensation frequency.

### Bench verification (always required)
- Square wave test at 1kHz — clean edges = stable, ringing = insufficient phase margin
- Frequency sweep 20Hz–200kHz — no peaks = adequate phase margin
- Capacitive load test — stability under reactive loads

---

## Push-Pull Center Tap Identification

For transformer-coupled push-pull, the center tap must have **equal turns on each side**. Never assume geometric or impedance midpoint without verifying from turns counts.

### Derivation from CVT or tapped transformer specs

Given: source voltage V_s, tap power ratings P_tap, secondary impedance Z_s

**Z_primary_tap = V_s² / P_tap**

**Np/Ns_tap = √(Z_primary_tap / Z_s)**

**Turns_tap = Np/Ns_tap** (normalized, relative)

### Finding valid center taps

For each tap T_ct to be a valid center tap with lower tap T_low and upper tap T_high:

**Turns_ct - Turns_low = Turns_high - Turns_ct**

Check ALL combinations including common (0 turns) as lower tap — this is frequently the most useful configuration and is easily overlooked.

### Example: Jensen CVT at 25V, 8Ω secondary

| Tap | Z_primary (Ω) | Turns (normalized) |
|---|---|---|
| Common | 0 | 0 |
| 4W | 156 | 4.42 |
| 2W | 313 | 6.25 |
| 1W | 625 | 8.84 |
| ½W | 1,250 | 12.5 |
| ¼W | 2,500 | 17.68 |
| ⅛W | 5,000 | 25.0 |

Valid push-pull configurations (equal turns each side of CT):

| Q1 (lower) | CT → V_supply | Q2 (upper) | Z_half (Ω) |
|---|---|---|---|
| Common | 4W tap | 1W tap | 156 |
| Common | 2W tap | ½W tap | 313 |
| Common | 1W tap | ¼W tap | 625 |
| Common | ½W tap | ⅛W tap | 1,250 |

The turns spacing between adjacent taps scales as √2 (each tap halves power, requiring √2 more turns) — so valid symmetric pairs always skip one tap when using common as lower terminal.

---

## Topology Checklists

### Power Stage Checklist
Before analyzing any output stage, confirm:
- [ ] Discrete transistors or IC?
- [ ] If discrete: NPN, PNP, or complementary pair?
- [ ] Push-pull or single-ended?
- [ ] Transformer-coupled or OTL?
- [ ] How many transformers? (driver + output?)
- [ ] Driver transformer secondary resistance? (needed for r_o_effective)
- [ ] Bias class (A, AB, B)?
- [ ] Emitter resistor present?
- [ ] Feedback: local only, or global enclosing output transformer?
- [ ] If push-pull: where is center tap? Verified from turns, not assumed?

### Full Circuit Checklist
- [ ] Supply voltage and polarity
- [ ] Number of gain stages
- [ ] Coupling method between stages
- [ ] All feedback paths identified and verified
- [ ] Circuit revision identified (germanium/silicon, discrete/IC)

---

## Describing Circuit Revisions

When a circuit has known revisions:
1. Describe each revision separately and clearly label them
2. Note what changed and why (parts availability, cost, sound)
3. Flag consequences of mixing components across revisions
4. Note polarity implications — PNP→NPN conversion requires reversing supply polarity, all electrolytic capacitors, and biasing diodes
5. Cite source for revision history

---

## Datasheet Reporting Format

**Minimum useful set:**
- Polarity (NPN/PNP)
- V_CEO
- I_C continuous and peak
- P_D
- h_FE range (min/typ/max at specified I_C)
- V_CE(sat)
- Package
- Complement part number

**Flag explicitly when absent:**
- Early voltage V_A (frequently absent in power transistors)
- h_oe output admittance
- Output curves (needed to derive r_o graphically if V_A absent)

---

## Source Quality Hierarchy

**For schematics:**
1. Manufacturer service manuals
2. SSGuitar.com (solid state guitar amp specific — excellent)
3. DIYAudio, Antique Radio Forums, Electro-Music
4. Guitar amp forums (The Gear Page, TalkBass)
5. Hobbyist schematic archives (verify against other sources)

**For datasheets:**
1. Manufacturer direct (ON Semi, ST, Vishay, TI)
2. Datasheetarchive.com, alldatasheet.com
3. Flag conflicting specs across manufacturers

**For transformer specs when datasheet unavailable:**
1. Back-calculate from rated power/voltage/load
2. DC resistance measurement (indicates winding ratio only, not impedance)
3. Forum measurements with LCR meter (cite source)
