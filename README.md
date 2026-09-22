# Gem Classifier

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
