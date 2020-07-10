# Handwriting Synthesis
<a href='https://github.com/sjvasquez/handwriting-synthesis/'>By sjvasquez</a>

Implementation of the handwriting synthesis experiments in the paper <a href="https://arxiv.org/abs/1308.0850">Generating Sequences with Recurrent Neural Networks</a> by Alex Graves.  The implementation closely follows the original paper, with a few slight deviations, and the generated samples are of similar quality to those presented in the paper.

Web demo is available <a href="https://seanvasquez.com/handwriting-generation/">here</a>.

## Usage
```python
lines = [
    "Now this is a story all about how",
    "My life got flipped turned upside down",
    "And I'd like to take a minute, just sit right there",
    "I'll tell you how I became the prince of a town called Bel-Air",
]
biases = [.75 for i in lines]
styles = [9 for i in lines]
stroke_colors = ['red', 'green', 'black', 'blue']
stroke_widths = [1, 2, 1, 2]

hand = Hand()
hand.write(
    filename='img/DEMO.svg',
    lines=lines,
    biases=biases,
    styles=styles,
    stroke_colors=stroke_colors,
    stroke_widths=stroke_widths
)
```
![](img/DEMO.svg)

Currently, the `Hand` class must be imported from `DEMO.py`.  If someone would like to package this project to make it more usable, please [contribute](#contribute).

A pretrained model is included, but if you'd like to train your own, read <a href='https://github.com/sjvasquez/handwriting-synthesis/tree/master/data/raw'>these instructions</a>.

## Demonstrations
Below are a few hundred samples from the model, including some samples demonstrating the effect of priming and biasing the model.  Loosely speaking, biasing controls the neatness of the samples and priming controls the style of the samples. The code for these demonstrations can be found in `DEMO.py`.

### Demo #1:
The following samples were generated with a fixed style and fixed bias.
![](img/BIAS-f-STYLE-f.svg)

### Demo #2
The following samples were generated with varying style and fixed bias.  Each verse is generated in a different style.
![](img/BIAS-f-STYLE-v.svg)

### Demo #3
The following samples were generated with a fixed style and varying bias.  Each verse has a lower bias than the previous, with the last verse being unbiased.
![](img/BIAS-v-STYLE-f.svg)