---
framework_version: 1.0.0
---

# Interview Preparation Guide

<!-- SETUP: STAR examples are personalized by running /setup based on your actual experience -->

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

<!-- Built from Kyle's resume and capstone report. Facts only; items marked (Kyle to add) need his own details before use. -->

### 1. Capstone AI camera + Android app (system integration, testing under a spec)
**S:** Senior capstone (ECEN 403/404, team of 4): an off-grid solar home lighting and security system. The team needed live camera monitoring, AI alerts and remote light control from a phone.
**T:** Kyle owned the Android Application + AI Camera subsystem, with requirements for streaming latency, AI response time and connection reliability.
**A:** Built a Kotlin Android app, streamed MJPEG from an ESP32-CAM (XIAO ESP32-S3 Sense) over local Wi-Fi, connected a Flask backend for AI scene analysis and Firebase for storage, and added remote lighting control. Instrumented the app to log FPS, time-stamp the AI pipeline and count connection attempts.
**R:** 2.3 s average AI analysis latency against a < 5 s target (10 trials); 92% connection reliability (23/25); stable frame rate over a 60 s test.
**Use for:** "Tell me about a technical project you're proud of", "How do you test/validate your work?", "Tell me about working on a team"
**(Kyle to add):** the hardest bug or integration problem and how you solved it; how you coordinated interfaces with teammates.

### 2. Hydraquip schematics + BOMs (design work, efficiency)
**S:** Summer 2025 internship at an industrial electrical systems shop in Houston handling large industrial projects.
**T:** Produce and revise AutoCAD schematics and BOMs for 15+ projects with UL-compliant components, and support panel build and QC.
**A:** Created and revised complex schematics in AutoCAD, built BOMs with correct UL sourcing, wired panels and subpanels, and ran QC checks to UL standards.
**R:** Reduced production time by up to 20% through schematic work; 15+ projects supported.
**Use for:** "Tell me about your design experience", "Describe a time you improved a process", "Attention to detail / quality"
**(Kyle to add):** what specifically about your schematics cut production time (clearer layouts, standard templates, fewer revisions?).

### 3. Hydraquip customer-facing work (communication)
**S:** Large-scale industrial customer projects at Hydraquip.
**T:** Support technical communication with customers.
**A:** Attended sales calls, provided demos, gathered specifications and relayed customer feedback to the engineering side.
**R:** Specifications gathered successfully for the projects supported.
**Use for:** "Explain something technical to a non-technical person", "Working with customers", "Sales/applications engineer fit"
**(Kyle to add):** one specific customer interaction and its outcome.

### 4. REAPERlab Modbus data logging (automation, learning fast)
**S:** Research lab needed automated collection of electrical measurements from an Eaton PXG1000 gateway and connected meters.
**T:** Build the logging system.
**A:** Wrote a Python Modbus TCP logger reading COM1/COM2, built a Raspberry Pi polling workflow across device IDs at 10-20 s intervals, and mapped 60+ registers (voltage, current, THD, harmonic power, frequency, energy) from the PXM/AcuDC documentation.
**R:** Automated CSV logging of power-quality data across multiple meters.
**Use for:** "Learning a new system quickly", "Automating a manual task", "Power quality / metering knowledge"

### 5. Arena Energy rig cost analysis (data analysis, presenting)
**S:** 2022 data engineering internship at an offshore oil and gas operator.
**T:** Analyze rig costs across Gulf of Mexico locations.
**A:** Used SQL, Excel and Python to reverse-engineer rig prices from location, size and water depth.
**R:** Delivered a technical presentation of the analysis to the engineering team.
**Use for:** "Data analysis experience", "Presenting to senior engineers"

### 6. Brazos Valley Food Bank (leadership, logistics)
**S/T/A/R:** Volunteered Sep 2023 - May 2026; directed 200+ food ticket orders weekly and coordinated kitchen and delivery logistics supporting 3,000+ meals per month.
**Use for:** "Leadership", "Working under pressure", "Organization"

## Common Tough Questions

### "What have you been doing since you graduated in May?"
> Kyle's resume does not list his short post-graduation role. If asked directly, **answer honestly**: he worked as an engineer at Freese and Nichols after graduating and was let go in a layoff about four months in. Keep it brief and neutral, then pivot to FE prep (exam January 2027) and his job search. Never deny or misdate the role - on any application form asking for full employment history, list it.
> (Kyle to add: your exact title and dates there.)

### "Why did you leave [previous company]?"
> For Freese and Nichols: "My position was affected by a layoff." No negativity; pivot to what you're looking for next.

### "You don't have [specific skill/experience]."
> Acknowledge the gap, bridge to adjacent experience (e.g. no PLC experience yet -> Modbus device polling, VFDs, controls coursework A, embedded control in capstone), and show willingness to learn.

### "Where do you see yourself in 5 years?"
> Licensed or on the PE track (FE in January 2027), owning design work on real projects, and trusted with both design and field responsibilities.

### "What's your biggest weakness?"
> (Kyle to add: a genuine one with a concrete mitigation.)

### "Why this company specifically?"
> Customize per company. Must reference: specific projects, company values, market position, or team structure. Never give a generic answer.

## Questions You Should Ask Interviewers

### About the Role
- "What does a typical week look like in this role?"
- "What would success look like in the first 6 months?"
- "What's the biggest challenge the team is facing right now?"

### About the Team
- "How big is the team, and how do you divide work?"
- "What does the development/project lifecycle look like, from idea to production?"
- "How do you onboard new team members?"

### About Tech & Growth
- "What's your current tech stack for [relevant area]?"
- "Is there room to grow into more architectural or strategic decisions?"
- "How does the team stay current with new tools and methods?"

### About Culture (use these to prevent disappointment)
- "How would you describe the team culture?"
- "What does professional development look like here?"
- "Is there flexibility for remote/hybrid work?"
- "What's the balance between development/new projects and maintenance work?"
- "How would you describe the leadership style in this team?"
- "What do people who thrive here have in common?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"

## After the Application (Best Practice)

### Follow-Up Etiquette
- **Don't call to "stand out"** or to learn more about the role post-submission - this risks a negative impression
- If the employer specified a timeline, respect it and wait
- If no timeline was given and significant time has passed (2+ weeks), a brief call to ask about status is acceptable
- If you have genuinely new, relevant information to share, a short follow-up is fine

### Thank-You Notes
- When you receive any update (interview invitation, rejection, or status update), send a brief thank-you message
- Express appreciation for their time and the process
- Keep it short (2-3 sentences)

## Roleplay Guidelines
When the user asks for interview practice:
1. Ask which role/company to simulate
2. Start with easy warm-up questions ("Tell me about yourself")
3. Progress to role-specific technical questions
4. Include 1-2 behavioral questions using the competencies from the job posting
5. End with a tough question or curveball
6. After each answer, give brief feedback: what worked, what to sharpen
7. Suggest which STAR example would work best for each question
