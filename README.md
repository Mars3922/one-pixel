# Gem Classifier

## Purpose

Gem Classifier is a small, playful machine learning page that predicts **Diamond** or **Quartz** from two gem properties: refractive index (RI), which describes how much light bends, and specific gravity (SG), which describes density compared with water. It helps visitors explore how labeled examples influence a model's answer.

## Open and use the page

Open the [Gem Classifier on GitHub Pages](https://mars3922.github.io/one-pixel/gem-classifier.html), or double-click `gem-classifier.html` to open the local file in a browser. No installation, API keys, or build step is needed; the local page also works offline.

1. Type values or drag the sliders: **RI 1.400-2.800** and **SG 2.20-6.10**, with steps of 0.001.
2. Watch the prediction, distances, chart, and gem illustration update. Higher RI brightens the gem's facets; higher SG lowers its side of the balance.
3. Compare your gem with the example dots. Blue areas predict Diamond; pink areas predict Quartz. Their shared edge shows where the prediction changes.
4. Try the preset buttons, change an example's label, or choose your own label and click **Add labeled gem** to see how teaching the model changes its answer.
5. Open the expandable explanations to learn more. Use **Reset to starter gems** to start over. Your experiments are not saved when you reload the page.

## How it makes a prediction

The model learns from 20 labeled starter gems. It scales RI and SG to the same 0-1 range so SG's larger numeric range does not dominate the comparison. It then finds the average position of each group and measures how far your gem is from those two averages.

The closer group becomes the prediction: Diamond or Quartz. The displayed distances explain the choice; a smaller distance means a closer match, not a confidence percentage. Changing the examples or their labels updates the averages and the chart's decision boundary. Equally close groups produce a tie, and the model needs at least one example of each label to compare them.

## A limitation I discovered

The model can only choose Diamond or Quartz; it has no label for other materials. When I tried moissanite, a diamond simulant, it was predicted as Diamond because the model forced it into one of the two available labels. A close match to the Diamond examples is not proof that a gem is a diamond.

## Development Log

1st prompt:
Ask for a first version that classifies Diamond vs Crystal from RI and SG, and shows the distances on chart as the reason for its prediction. 
Also want the website to be capable of telling people what is a diamond.

2nd prompt:
I found that the ranges were set too narrow, so I asked Codex to widen them and scale both features.
A few more examples are added to the starter gems.

3rd prompt:
Update the input labels since they didn't change along with the ranges.

4th prompt:
The page only showed numbers and dots, which felt abstract for gems, so I asked Codex to draw a gem icon to make the input more direct.
The icon did not match what RI and SG actually mean, so I asked Codex to make higher RI brighten the gem's facets and higher SG tilt a balance scale, without changing the gem's size.

5th prompt:
The chart did not show where the model switches its answer, so I asked Codex to shade the background blue for Diamond and pink for Crystal to reveal the decision boundary.

6th prompt:
A gemologist classmate pointed out that "Crystal" was ambiguous, and what I meant was quartz, so I asked Codex to rename the label to "Quartz" and remove the confusing note.

7th prompt:
I showed the page to two classmates: the gemologist understood it quickly, but another classmate found it hard to follow, so I asked Codex to simplify the page by enlarging the gem icon, shrinking the explanation text, and collapsing the long sections.

8th prompt:
Typing exact numbers was the only way to change the inputs, so I asked Codex to add a slider next to each input that stays in sync with the number box and updates the prediction live.
