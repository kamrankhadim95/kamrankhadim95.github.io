# Kamran Khadim — Portfolio

Single-page portfolio served by GitHub Pages at `https://kamrankhadim95.github.io`.

All content lives in the data block at the top of the `<script>` in `index.html` (`PROFILE`, `SKILLS`, `PROJECTS`, `EXPERIENCE`, `ACHIEVEMENTS`). Edit that block only; the page renders from it.

## Assets

| File | Used for | If missing |
|---|---|---|
| `assets/hero.mp4` | Animated 3D avatar in the hero | Falls back to `assets/hero.png` |
| `assets/hero.png` | Still avatar | Dashed placeholder |
| `assets/photo.jpg` | Photo on the ID card | Initials |
| `PROJECTS[].image` | Screenshot in each Work card | "Add a screenshot" box |

The hero video uses `mix-blend-mode: multiply`, so its white background disappears into the cream page. Use a plain white or light background, portrait or 9:16, under ~8 MB.

## Making the 3D avatar video

1. **Character image** — in an image generator (ChatGPT, Gemini or similar), upload a reference image of the style you want plus a clear full-body photo of yourself, and prompt:

   > Create a premium, high-quality 3D cartoon-style full-body character portrait using the two uploaded images: use the first image as the exact visual reference for composition, outfit, pose, framing and background; use the second image as the identity reference. One person standing upright, centred in a 9:16 portrait frame, full body visible head to feet, white button-up shirt with rolled sleeves, dark trousers, white sneakers, against a clean plain pure-white background with a soft natural ground shadow. Keep the person's face, hairstyle, skin tone and body shape recognisable. No text, no props, no extra characters.

   Save it as `assets/hero.png`.

2. **Animate it** — in Google Flow (Veo) or any image-to-video tool, upload `hero.png` and prompt:

   > The character looks at the camera, smiles, waves hello, then gestures with an open hand to the left as if presenting. Camera locked, background stays pure white, no camera movement. NO background music, NO sound effects, NO text.

   Export as MP4 and save as `assets/hero.mp4`.

## Publishing on GitHub Pages

1. Create a **public** repo named exactly `kamrankhadim95.github.io`.
2. Push this folder to it (commands below).
3. Repo → **Settings → Pages** → Source: **Deploy from a branch**, Branch: **main / (root)**.
4. The site is live at `https://kamrankhadim95.github.io` within a couple of minutes; every push redeploys it.

```bash
cd ~/portfolio-site
git init -b main
git add .
git commit -m "Portfolio site"
git remote add origin https://github.com/kamrankhadim95/kamrankhadim95.github.io.git
git push -u origin main
```

## Preview locally

```bash
python3 -m http.server 8765 --directory ~/portfolio-site
```

Then open `http://localhost:8765`.
