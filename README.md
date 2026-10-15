# Coral Link Builder

Paste Coral pseudocode (and optional program input) and get a link that opens it in the
[zyBooks Coral simulator](https://coral-sim.zybooks.com/), ready to paste into a textbook.

## What it does

- Rebuilds every indent as an exact multiple of 3 spaces. Text copied from LucidChart
  mixes non-breaking spaces into the indents, which makes the simulator stop with an error.
- Turns non-breaking spaces in the middle of a line into normal spaces, and drops trailing ones.
- Highlights any line whose indent still isn't a multiple of 3, so you can fix it by hand.
- Takes optional program input: numbers separated by spaces. Returns and extra spaces become
  single spaces, and anything that isn't a number is highlighted. With no input, `%20` is sent.
- Builds `https://coral-sim.zybooks.com/?input=<input>&code=<code>`, both parts URL-encoded,
  and copies the link.

Everything runs in the browser. Nothing you paste is sent anywhere or saved: the page opens
empty every time.
