---
name: paper-polish
description: Polish LaTeX paper text sentence by sentence for academic writing in superconducting quantum computation. Use when the user asks to polish, proofread, edit, copy-edit or improve the English of a LaTeX passage, section or .tex file for a paper or thesis. Checks grammar, title capitalization, figure-caption consistency, terminology and hyphenation without changing the physics, equations or LaTeX, and returns a list of revisions followed by the fully corrected LaTeX.
---

# Paper polish

Go through the given LaTeX paper text sentence by sentence and polish it for academic scientific writing in superconducting quantum computation.

The text may be pasted directly, or given as a `.tex` file, a section of one, or a line range. If it is a file, read the requested part. Do not edit the file unless the user asks you to apply the revisions; by default, report them as described under **Output format**.

## Items to check

1. **Grammar and mechanics**
   - Check and correct article usage, prepositions, capitalization, spacing, punctuation, verb tense, subject–verb agreement, singular/plural agreement, parallel structure and word choice.

2. **Section and subsection titles**
   - Check the capitalization of all section, subsection, paragraph, appendix and figure titles.
   - Use a consistent capitalization style throughout the text.

3. **Figures and captions**
   - Whenever a figure is included, check whether its caption uses the same notation, terminology, parameter definitions and scientific claims as the main text.
   - If the caption and main text are inconsistent, revise the caption to match the main text.
   - Check that all figure references, panel labels, symbols and quantities are accurate and consistent.

4. **Technical consistency**
   - Preserve and consistently use all technical terminology, equations, notation, symbols, citations, labels, cross-references and LaTeX commands.
   - Check that terminology is appropriate for a research paper or Ph.D. thesis in superconducting quantum computation.
   - Do not oversimplify technical terms such as dispersive coupling, flux noise, anharmonicity, cavity dephasing, transmon, fluxonium, bosonic encoding, Lindbladian, Floquet quasienergy and rotating-wave approximation.

5. **Clarity and academic style**
   - Make the writing concise, precise, natural and technically accurate.
   - Improve sentence flow and transitions when necessary, while keeping the revision as close to the original as possible.
   - Break overly long sentences into shorter sentences when this improves readability.
   - Remove redundancy and avoid using multiple words with nearly identical meanings.
   - Replace awkward or nonstandard phrasing with standard scientific language.

6. **Compound terms and hyphenation**
   - Avoid awkward compound-noun strings.
   - Use standard compound modifiers and hyphenation when appropriate, such as "matrix-vector", "time-dependent" and "cost-function".
   - Do not create unnecessarily long or nonstandard hyphenated expressions.

7. **Ambiguity**
   - If a sentence is ambiguous, choose the revision that best matches the surrounding context and standard usage in superconducting quantum computation.
   - Point out any ambiguity that cannot be resolved reliably from the provided context.

## Constraints: do not

1. Do not change the technical content or underlying physics claims.
2. Do not add new scientific claims, physical interpretations, assumptions, references, derivations or explanations, unless a minimal clarification is necessary to make a sentence grammatical or unambiguous.
3. Do not alter equations, notation, symbols, citations, labels, references, figure numbers, equation numbers or LaTeX formatting, unless correcting an evident formatting or consistency error.
4. Do not replace specialized terminology with less precise or oversimplified language.
5. Do not make stylistic changes that unnecessarily move the revision away from the original meaning or structure.
6. Do not omit any sentence, equation, citation, label or technical detail from the original text.

## Output format

**Part 1: sentence-by-sentence review.** Identify every place that should be revised. For each item:

- Quote the original sentence or relevant phrase.
- Explain briefly what should be improved (grammar, clarity, consistency, notation, capitalization, redundancy, technical phrasing, ...).
- Give the proposed revision.

List ambiguities that could not be resolved from context separately at the end of Part 1.

**Part 2: corrected passage.** After the review, give the fully corrected version of the entire passage in LaTeX, in a single ```latex code block. Preserve all equations, citations, labels, references, environments and LaTeX commands.
