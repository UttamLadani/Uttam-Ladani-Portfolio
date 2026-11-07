# Uttam Ladani — Portfolio

Live Demo : https://uttam-ladani.vercel.app/

A single-page portfolio in a red & white editorial style. One cut-out portrait travels through every
section as you scroll (hero → about → work → journey → toolkit orbit → awards → contact).

Plain HTML, CSS and JavaScript. No build step and no dependencies.

## Folder structure

```
index.html          ← all content (text, links, projects, education, certificates)
css/style.css       ← design (colours, fonts, layout, animations)
js/main.js          ← scroll scenes, project stepper, skill orbit, counters, cursor
assets/uttam.webp   ← cut-out portrait used on the page (uttam.png = original cut-out / social preview)
assets/projects/    ← put project screenshots here (see README.txt inside)
assets/favicon.svg
```

## Run locally

Open `index.html` in a browser, or for best results serve the folder:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Deploy to Vercel

**Option A: drag and drop.** Go to vercel.com → Add New → Project, then drag in the whole `uttam-portfolio` folder.

**Option B: GitHub.**
1. Push this folder to a GitHub repository.
2. In Vercel, click **Add New → Project** and import the repository.
3. Framework preset: **Other**. Leave the build command empty and set the output directory to `./`.
4. Click **Deploy**.

To replace the current site, push these files to the repository that is already connected to
`uttam-portfolio-tau.vercel.app`.

## Common edits

| What | Where |
|---|---|
| Hero text and buttons | `index.html` → section `#home` |
| About paragraphs and quick facts | `index.html` → section `#about` |
| Projects (title, text, tags, links) | `index.html` → section `#work`, one `<article class="project">` each |
| Education and experience timeline | `index.html` → section `#journey` (`data-year` = big outlined number) |
| Skills orbiting the photo | `index.html` → `.orbit-field` (`data-ring` 0/1/2 = inner/middle/outer ring, `hot` = red pill) |
| Stats and certificates | `index.html` → section `#awards` |
| Email, phone, LinkedIn, GitHub | `index.html` → section `#contact` |
| Brand red | `css/style.css` → `--red` at the top |
| Where the photo sits in each section | `css/style.css` → `body[data-scene="..."]` rules (`--x` position, `--s` scale) |

### Adding a 5th project
Copy one `<article class="project">` block, then update the counter text `/ 04` → `/ 05` and
`style="--n:4"` → `--n:5` on the `#work` section.

### Changing the photo
Use a photo with a transparent background (PNG/WebP, head and shoulders, cut at the bottom edge)
and save it as `assets/uttam.webp`.

## Notes
- On screens under 1000px the travelling photo becomes inline images and the layouts stack for mobile.
- Respects "reduce motion" system settings.
