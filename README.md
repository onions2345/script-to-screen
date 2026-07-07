# 🎬 Script to Screen

**Turn any script into a voiced, illustrated video — free, in your browser, no signup.**

Paste a screenplay or story. It works out who speaks each line, gives every character its own voice, reads it aloud, sketches the visuals, and hands you the finished audio and images as a single video file.

**▶ Live:** https://onions2345.github.io/script-to-screen/

`Free` · `No account` · `Runs in your browser` · `One HTML file` · `Open source`
 
You can download it and ask claude to edit it to make it better for yourself, welcome to submit an update here. 

---

## What it does

- **🧠 Understands the script** — an AI reads your text and figures out the narrator, each character, and the on-screen/system lines. Any format works: labelled (`NARRATOR:` / `ON SCREEN:`) or plain prose.
- **🎙️ Voices it** — every character is cast to its own HD voice; system lines get a flat robotic read. All lines are stitched into one track.
- **🖼️ Illustrates it** — generates a cinematic image for each visual beat.
- **📦 Exports it** — download the whole soundtrack as **WAV** (lossless) or **MP3** (small), export a self-contained **storyboard HTML** (images + lines + audio in one file), or render the whole thing as a **video (WebM)** you can just press play on.

---

## How to use

1. Open the live link above.
2. Get a free Gemini key from **[Google AI Studio](https://aistudio.google.com/apikey)** → sign in → *Create API key* → paste it into the app.
3. Paste your script (or hit **Load sample**) → **Analyze script**.
4. Tweak the voice cast if you want, then **Generate voices** and **Generate visuals**.
5. Grab the result: **Download WAV / MP3**, or **Export storyboard (HTML)**.

That's it — nothing installs, nothing uploads anywhere except Google's API.

---

## Why this one

- **Actually free.** No subscription, no trial, no watermark on the audio. You bring your own free Gemini key, so it costs the maker nothing to keep online and costs you nothing to use.
- **No signup wall.** Most "free" voice tools cap you at a few thousand characters, hide the good voices behind a paywall, or make you create an account. This doesn't.
- **Three tools in one.** Plenty of sites do text-to-speech. This one *parses the script, casts the voices, and draws the visuals* in a single page — I haven't found another free, no-signup tool that does all three together. If you find one, I'd genuinely like to see it.
- **Your data stays yours.** It runs entirely client-side. Your key lives only in your browser; your script goes straight to Google and nowhere else.
- **One file, anywhere.** The whole app is a single `index.html`. Fork it, host it, hack it.

---

## How it works

Your browser talks directly to Google's Gemini API with your key:

1. A **text model** returns a structured breakdown (speakers, voices, on-screen lines, visual beats).
2. The **TTS model** voices each line; raw audio is wrapped to WAV in-browser and concatenated. MP3 is encoded on the fly with [`@breezystack/lamejs`](https://www.npmjs.com/package/@breezystack/lamejs).
3. The **image model** draws each visual beat.

No server, no build step. That's why it hosts for free on GitHub Pages.

---

## Run your own copy

1. Create a public repo and add `index.html`.
2. **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)` → Save.**
3. Open `https://<your-username>.github.io/<repo>/`.

---

## A note on your API key 🔑

GitHub Pages is **public**, so never paste your key into a committed file — the app asks for it at runtime and keeps it only in your browser (localStorage). For extra safety, restrict the key to your Pages URL in **Google Cloud Console → Credentials → HTTP referrers**.

---

## Why I built it

I kept hitting paywalls and tiny character limits on every "free" voice site, and none of them could take a whole script with different characters and just *do it*. So I built the tool I wanted — free, open, and all in one page. I think it's the best free option I've come across. 

*Built by [https://mvandiermen.com/](https://mvandiermen.com/).*
