# Rules for structuring any subject in this repository

This file is a reusable specification for adding a subject from first principles through advanced study. Follow it for Mathematics and for any future subject.

## Scope and hierarchy

1. Start with prerequisites and a learner-facing `README.md` that explains the order and branching points.
2. Divide the subject into major domains, then areas, then narrow study units. Use numbered directories for a sensible default sequence, such as `Subject/06_Calculus/01_Single_Variable/02_Differentiation/book_name.txt`.
3. A leaf is narrow enough to finish as a focused study unit. `Calculus` alone is too broad; `chain rule and implicit differentiation` is appropriately specific. If a unit has unrelated objectives, split it again.
4. Cover definitions, examples, techniques, proofs, counterexamples, applications, and limitations. Include both elementary and advanced branches; add missing prerequisites instead of assuming them away.
5. Cross-link prerequisites and continuations in the subject README. Avoid claiming that a finite outline contains every possible theorem or new research area.

## Required `book_name.txt` in every leaf

Use this format:

Primary book: Full title — author(s), edition if important.
Read: exact section titles or chapter themes; give page numbers only when the edition is fixed and verified.
Study checklist:
01. A named, testable concept or skill.
02. ...
Completion: a concrete exercise, proof, computation, or project that shows mastery.

Aim for 6–12 ordered checklist items. Name the content to read rather than merely listing books or page ranges. Identify optional deeper books as `Extension book`, not as extra mandatory full-book assignments. If a topic is absent from the primary book, select a better source or a precise second source.

## Source quality and copyright

- Prefer legitimate open textbooks, university course texts, and well-established books; verify titles and topic coverage before adding them.
- Cite book title and author clearly. Do not invent precise chapter, section, or page numbers; editions differ.
- Do not upload or link to unauthorized copies of books, solution manuals, or paywalled text.
- Keep the repository as metadata and study guidance. Link to an official or legitimate open source when known.

## Quality check for new units

- The folder is placed after its prerequisites and has one `book_name.txt`.
- Its checklist is granular enough that a learner knows what to study next.
- A reader can tell when the unit is complete.
- Terminology and notation agree with neighboring units; cross-links point to real paths.
- The subject README lists the new area and explains its role in the learning path.
