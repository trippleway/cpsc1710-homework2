# Beat Vibe Classifier

## Name and purpose

**Beat Vibe Classifier** is a small, playful webpage that classifies a short beat as **chill** or **hype**. It uses two inputs—tempo in beats per minute (BPM) and energy on a scale from 0 to 10—to make its prediction.

## How to open and use the page

1. Open `beat-classifier.html` in Chrome, Safari, or Firefox. No installation, API key, or build step is needed.
2. Use the tempo and energy sliders to describe a beat. You can press Tab to focus a slider and use the arrow keys to change it.
3. Guess whether the beat is chill or hype, then choose a button to reveal the model's prediction and see whether your guess matched.
4. Use the reset button to return to 70 BPM and energy 2, or click either learned example to try it.

## How the classifier makes a prediction

The classifier compares the beat with two learned examples: a chill beat at 70 BPM with energy 2, and a hype beat at 140 BPM with energy 9. It calculates how far the beat is from each example while weighing tempo and energy together. The closer example decides the prediction; if both examples are almost equally close, especially around 105 BPM with middle energy, the model says it is unsure.

## Limitation discovered

The model only looks at two numbers—tempo and energy. It does not consider other parts of real music, such as melody, instruments, or the emotion of lyrics, so it may not classify some real songs accurately: for example, a slow but intense song or a fast but calm song.

模型只看两个数字（tempo 和 energy），没考虑真实音乐的其他面向（旋律、乐器、歌词情绪等），所以对某些「慢但很躁」或「快但很平静」的真实歌曲可能判断得不准。

## Development Log

- Directed Codex to create a first version with tempo and energy sliders, a chill/hype prediction, visible scores and distances to two learned examples, and a reason for each prediction.
- Tested the extreme input of tempo 180 and energy 0, noticed that the progress bar and text prediction could disagree because they used different scoring formulas, and directed Codex to use one shared distance-based score.
- Directed Codex to add a reset button, confirm keyboard slider navigation, and provide a visible focus outline for keyboard users.
- Directed Codex to add a “guess first” interaction so visitors choose chill or hype before the model reveals its prediction.
- Showed the page to a classmate without explaining it first. They understood the sliders and the basic comparison logic, but were confused by the unexplained “distance” and “points” numbers, and noted that the “Why might it be unsure?” note only covered the 105 BPM case, not conflicting-clue cases like fast tempo with low energy. Directed Codex to add a plain-language explanation of what the numbers mean and expand the “unsure” explanation to cover conflicting clues.

## Credits

Materials are by [Xiuye Chen](https://github.com/xiuyechen), developed with Codex, and shared under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
