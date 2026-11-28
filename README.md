# BEC755D · Sensors and Actuators — lecture series site

Free, module-wise video lecture series for **VTU BEC755D Sensors and Actuators**
(Semester VII, Scheme 2022, Credits 03).

- 5 modules · 40 lectures, in syllabus order
- Module-wise notes on Zenodo (one DOI per module)
- Classroom presentations on Google Drive (one deck per module)
- Solved question bank: previous 4 years, 3 hours, CO1–CO5
- CO mapping: M1 → CO1, M2 → CO2, M3 → CO3, M4 → CO2 & CO3, M5 → CO5

**Live site:** https://bec755d-lectures.onrender.com

---

## What is in this repository

| File | Purpose |
| --- | --- |
| `index.html` | The whole site — HTML, CSS and JS in one self-contained file |
| `dr_lokesh_professor_new.png` | Profile photo used in the teacher section |
| `render.yaml` | Render Blueprint (static site, cache headers) |
| `robots.txt` | Allows all crawlers |
| `.nojekyll` | Not needed by Render; keeps GitHub Pages from processing the files |

There is no build step. Render serves these files exactly as they are.

---

## Deploying on Render

### Option A — Blueprint (recommended, uses `render.yaml`)

1. Push this folder to a GitHub repository (see below).
2. Open <https://dashboard.render.com> → **New** → **Blueprint**.
3. Connect the repository. Render reads `render.yaml` and shows the service
   `bec755d-lectures`.
4. Click **Apply**. First deploy takes about a minute.
5. Your site goes live at `https://bec755d-lectures.onrender.com`.

### Option B — manual static site

1. **New** → **Static Site** → connect the repository.
2. Fill the form exactly like this:

   | Field | Value |
   | --- | --- |
   | Name | `bec755d-lectures` |
   | Branch | `main` |
   | **Root Directory** | *(leave empty)* |
   | **Build Command** | *(leave empty)* |
   | **Publish Directory** | `.` |

3. **Create Static Site.**

> The single most common mistake is putting `render.yaml` (or `bec755d-repo`)
> in the Publish Directory. It must be `.` — the folder that contains
> `index.html`.

### After the first deploy

- Copy the live URL Render gives you.
- Replace the guessed canonical URL in `index.html`:

  ```html
  <link rel="canonical" href="https://YOUR-URL/" />
  <meta property="og:url" content="https://YOUR-URL/" />
  ```

  Then commit and push — Render redeploys automatically on every push.
- Optional: **Settings → Custom Domain** to use your own domain, and
  **Settings → Health Check Path** = `/index.html` if you want deploy gating.

---

## Pushing this folder to GitHub

From inside this folder:

```bash
git init
git add .
git commit -m "BEC755D Sensors and Actuators — lecture series site"
git branch -M main
git remote add origin https://github.com/lokeshmr23/bec755d-lectures.git
git push -u origin main
```

Create the empty repository first at <https://github.com/new> —
name it `bec755d-lectures`, keep it **Public**, and do **not** add a README
(otherwise the first push is rejected as non-fast-forward).

If you already have a repository with other courses, put this folder in a
subfolder and set Render's **Root Directory** to that subfolder instead, with
Publish Directory `.` inside it.

---

## Editing content

All course data lives in **one `MODULES` config** at the top of the `<script>`
block in `index.html`:

```js
const MODULES = [
 { id:1, title:"Sensors and Transducers; Measurement", hours:8, co:"CO1",
   notes:"https://doi.org/10.5281/zenodo.24338582",
   slides:"https://drive.google.com/file/d/.../view?usp=drive_link",
   qbank:"https://doi.org/10.5281/zenodo.24624208",
   lectures:[
  {code:"M1-L1", topic:"Introduction to sensors and transducers", url:"https://youtu.be/He8kmNzw0zI"},
  ...
 ]},
];
```

- Fix or add a lecture → edit that module's `lectures` array.
- Change notes / slides / question bank → edit `notes`, `slides`, `qbank`.
- Empty string = that button disappears for that module.

---

## Placeholders still open

| Placeholder | Where |
| --- | --- |
| `[Add institution]` | Teacher section |
| `[Add institution]` | Footer blurb |
| Canonical + `og:url` | `<head>` — replace the guessed Render URL |

Nothing on the page claims pass rates, rankings, fees, video durations,
publication counts or VTU rules.

---

## Licence / disclaimer

Materials are for educational use and follow the VTU Scheme 2022 BEC755D
syllabus. Always refer to the official VTU syllabus and your instructor's
guidance for the latest updates.
