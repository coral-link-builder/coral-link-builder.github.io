# Coral Link Builder

Paste Coral pseudocode and get a link that opens it in the
[zyBooks Coral simulator](https://coral-sim.zybooks.com/), ready to paste into a textbook.

## What it does

- Rebuilds every indent as an exact multiple of 3 spaces. Text copied from LucidChart
  mixes non-breaking spaces into the indents, which makes the simulator stop with an error.
- Turns non-breaking spaces in the middle of a line into normal spaces, and drops trailing ones.
- Highlights any line whose indent still isn't a multiple of 3, so you can fix it by hand.
- Encodes the code onto `https://coral-sim.zybooks.com/?input=%20&code=` and copies the link.

Everything runs in the browser. Nothing you paste is sent anywhere or saved: the page opens
empty every time.
