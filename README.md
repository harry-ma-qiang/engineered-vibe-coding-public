# Engineered Vibe Coding (EVC)

Engineered Vibe Coding is a way of building software with AI coding agents so
that the result reads like careful work by a senior engineer, not like a pile
of generated code. "Vibe coding" means letting an AI write the code from a
loose description; EVC keeps that speed but adds the discipline of a real
engineering team.

## How it is designed

- **Requirements first, each traced to its source.** Every requirement quotes
  the sentence of the design document it comes from. Nothing is added
  silently: a gap becomes a question for a person, or an explicit assumption
  that can be withdrawn later.
- **Check the requirements before writing code.** Behaviour written as state
  tables is turned into a model that a checker explores for unreachable
  states, dead ends and conflicts.
- **Small steps, each closed by a gate.** Eight steps: study the design
  documents, write requirements and acceptance scenarios, check them, write
  algorithm cards, design the code, write tests first and then the code, run
  end-to-end tests written by someone who did not write the code, and look
  back. A program, not an AI, decides whether a step passes; a fresh reviewer
  then reads the result.
- **The gates are tested too.** Each gate has good and bad examples. A gate
  that lets a bad example through is treated as a bug.
- **Count what escaped.** Every defect records the step that should have
  caught it, so the process gets better exactly where it leaks.
- **Searchable maps of documents and code** show what a change touches and
  what existing code can be reused instead of written again.

In a first trial on a real feature in a large Rust code base, two blind
reviews rated the EVC version clearly above a version written the usual way,
and most defects were found before any code existed. It also took much
longer; making it cheaper is the current work.

## Status

An early, personal project. The tool is not released yet: a binary is
coming. Check each download against its published SHA-256 checksum before you
run it.

## License

Released artifacts: EVC Binary License 1.0 (see LICENSE).
