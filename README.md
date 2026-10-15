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

## Publishing on GitHub Pages

The whole site is the single file `index.html`. Push this folder to a GitHub repository, then
under **Settings → Pages** choose **Deploy from a branch**, branch `main`, folder `/ (root)`.

## Editing `index.html`

- The page has a Content-Security-Policy that only lets its own script run, by matching a
  SHA-256 hash of that script. **If you change anything between `<script>` and `</script>`,
  the hash must be updated or the page will stop working.** The browser console names the
  new hash it expected; copy it into the `script-src 'sha256-…'` part of the policy.
- In the script, non-breaking spaces are written as ` `. Keep them written that way,
  never as the invisible character itself, which editors can silently turn into a normal space.
