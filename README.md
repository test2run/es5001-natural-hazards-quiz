# ES5001 — Natural Hazards Concept Quiz

A self-quizzing tool for **ES5001/ES7001 Natural Hazards & Society**, covering the lecture notes for Weeks 1–7, 9–11 and 13.
It runs on the same app as the [BF3122 Carbon Markets quiz](https://github.com/test2run/bf3122-carbon-markets-quiz-2).

**352 multiple-choice questions** (189 of them hard), at least 20 per lecture, plus a set that links hazards across weeks.
There is no Week 8 (recess) or Week 12 lecture in the notes this quiz was built from.

Every question tests concepts, mechanisms and how to apply them: telling apart terms that are easy to confuse,
predicting what changes when one factor changes, diagnosing why a scenario turned out the way it did. No question
asks for the date, magnitude, death toll or temperature of a particular disaster. The one exception to "no numbers"
is the magnitude–energy relationship (each whole-number step is about 32 times the energy), which the lecturer flagged
as examinable.

Options are written to compete with each other. In every question the longest option is at most 1.4× the shortest,
and the correct answer is the longest option in about 18% of questions and the shortest in about 22%, so length
gives nothing away. Answer positions A–D are evenly spread.

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
| 5 | How magma forms & tectonic settings · Hotspots · Silica, viscosity & igneous rocks · Volcano shape & eruption style | 29 |
| 6 | Lava, ash fall & gases · Pyroclastic flows, surges, lahars & collapse · Monitoring volcanoes · Forecasting & hazard zones | 33 |
| 7 | Forces on a slope · Water, cohesion & liquefaction · Types of mass movement · Monitoring & mitigation · Cascading hazards | 37 |
| 9 | Weather vs climate · Rising air & clouds · Atmospheric cells, winds & Coriolis · Monsoons, ITCZ, ENSO & IOD | 34 |
| 10 | Cyclone names & ingredients · Structure · Hazards & impacts · Warning & mitigation · Thunderstorms, lightning & hail | 35 |
| 11 | Deltas · Storm surge & compound flooding · Drivers of sea-level change · Subsidence · Responding to sea-level rise | 27 |
| 13 | Greenhouse effect & feedbacks · Extremes & heatwaves · Sea-level rise · Past climate & projections · Peatlands | 25 |
| Cross-week | Mechanisms that link hazards across the course (fluid pressure, Coriolis, baselines, vulnerability…) | 16 |

Content is drawn only from the lecture slides and their annotations. Slides marked "must know", "test question",
highlighted or starred get more weight. Slides that only show case studies or photos are used for the concept they
illustrate, never for the facts of the event. Weeks 9, 11 and 13 had no annotations, so their questions follow each
lecture's learning objectives. Where the Week 5 slide had felsic and mafic swapped, the Week 6 correction is used.

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
