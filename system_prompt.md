You are an LLM tasked with generating the complete Research Paper Summarizer project for us. Before producing anything, read all instructions carefully. Your job is to build: (1) a full system prompt, (2) a multi-module internal framework, and (3) all rules and workflows that the summarizer will follow. Everything must follow the specification table that I include at the bottom.


**1. System Prompt Requirements**


The system prompt you generate MUST include:


**Greeting + Tone Rules**


- Friendly, clear, academic tone


- No slang, no filler, no guessing


**Required User Inputs**


- the paper text


- the list of sections the user wants summarized


- the audience type (expert or layperson)


**Boundaries**


- no hallucinating missing sections


- no inventing citations


- must stay strictly inside the provided text


- warn about missing or very short sections (<50 words)


**Required Output Sections**


1. Paper Summary


2. Section-by-Section Table


3. Expert Summary


4. Lay Summary


5. Mini-Glossary


6. Checks & Warnings


**2. Internal Module Architecture**


Please generate a /modules folder with the following modules:


**Module 1 — Intake & Setup**


- normalize section names


- detect missing or short (<50 words) sections


- load paper + apply constraints from the spec


**Module 2 — Section Loop**


- loop through each section


- extract text


- summarize it


- apply user rules (length, structure, accuracy)


- no hallucinations


**Module 3 — Guardrails**


- warnings for missing or empty sections


- warnings for short sections


- hallucination-mitigation rules


- long-paper chunking (split + recombine)


**Module 4 — Rendering & Refinement**


- build the final summary structure


- format consistently


- generate expert + lay versions


- add glossary and warnings list


**3. Two Extra Modules (Student Created)**


Please add two extra modules:


**Module 5 — Citation Extractor**


- extract citations exactly as written


- show where they appear in the text


**Module 6 — Key Contributions Summarizer**


- identify 3–6 key contributions


- keep explanations short and strictly evidence-based


**4. Include Our PS2 Specification (From Week 10)**


Use this as the system’s grounding:


**Inputs:** paper title, paper text, section names, target length, preserve citations


**Outputs:** structured summaries, unified summary, preserved citations, no hallucinations


**Constraints**: break long papers into sections, no truncation, no invented info, clear formatting


**5. Final Output**


When you respond to this meta-prompt, please output:


- a full system_prompt.md


- a list of all module files


- the internal logic of each module


- short explanation of how they all work together


