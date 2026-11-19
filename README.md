# ES5001 — Natural Hazards Concept Quiz

A self-quizzing tool for **ES5001/ES7001 Natural Hazards & Society**, covering the lecture notes for Weeks 1–7, 9–11 and 13.
It runs on the same app as the [BF3122 Carbon Markets quiz](https://github.com/test2run/bf3122-carbon-markets-quiz-2).

**116 multiple-choice questions** so far (Weeks 1–4; more weeks are being added).

Every question tests concepts, mechanisms and how to apply them: telling apart terms that are easy to confuse,
predicting what changes when one factor changes, diagnosing why a scenario turned out the way it did. No question
asks for the date, magnitude, death toll or temperature of a particular disaster. The one exception to "no numbers"
is the magnitude–energy relationship (each whole-number step is about 32 times the energy), which the lecturer flagged
as examinable.

Options are written to compete with each other. They are close in length and specificity, and the correct answer is
the longest option only about a quarter of the time, so length gives nothing away.

## Using it

Pick topics (or a week), choose **Instant** feedback for learning or **Exam** mode to simulate the real
thing, and go. You can navigate backwards. At the end you get a per-topic breakdown and a full review with a
rationale for *every* option, including why the near-miss distractors are wrong.

Keyboard: <kbd>1</kbd>–<kbd>4</kbd> to answer, <kbd>←</kbd> <kbd>→</kbd> to move.

## Topics

Mapped to the learning objectives slide of each lecture:

| Week | Topics | Qs |
|---|---|---|
| 1 | Hazards, disasters & uneven impacts · How geoscientists study Earth · Plate tectonics as a unifying theory | 20 |
| 2 | Earth's structure & mantle convection · Seafloor spreading & magnetic stripes · Plate boundaries · Elastic rebound & seismic waves · Fault types | 34 |
| 3 | Magnitude & Gutenberg–Richter · Magnitude vs intensity · Earthquake types, exposure & vulnerability · Tsunami generation & propagation | 31 |
| 4 | Earthquake cycle · GNSS, InSAR & seismometers · Aftershocks & subduction deformation · Warnings & risk reduction | 31 |

Content is drawn only from the lecture slides and their annotations. Slides marked "must know", "test question",
highlighted or starred get more weight. Slides that only show case studies or photos are used for the concept they
illustrate, never for the facts of the event.

## Files

```
index.html       markup + styles
app.js           quiz logic (vanilla JS, no dependencies)
questions.json   all content
```

To edit or add a question, edit `questions.json` only. Each entry:

```jsonc
{
  "id": "q001",
  "topic": "w01a",          // matches topics[].id
  "week": 1,
  "difficulty": 2,          // 2 standard · 3 hard
  "skill": "apply",         // apply | compare | predict | diagnose
  "stem": "…",
  "options": ["…","…","…","…"],
  "answer": 1,              // 0-based index into options
  "rationales": ["…","…","…","…"],   // one per option, same order
  "takeaway": "One-line principle.",
  "source": "W1 p9"         // slide provenance
}
```

The app reads the file at load, so a committed edit is live on the next refresh.

Run locally with any static server (opening `index.html` from disk will fail, because browsers block
`fetch` on `file://`):

```bash
python -m http.server 8000
```
