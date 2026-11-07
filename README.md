<p align="center"><img src="docs/cover.jpg" alt="Illustration of a browser window showing a long registration form with a campus banner, text fields, radio buttons, file upload boxes, a date picker, checkboxes and an orange submit button" width="100%"></p>

# Job Fair Registration Form

A single-page student registration form for a university job fair, built with HTML, CSS and JavaScript as web design coursework.

## What it does

`site/Main/Index.html` is one long form with a banner image at the top and five sections:

- **Student information:** first and last name, email, 10-digit phone number, gender (radio buttons), age and home address.
- **Upload section:** file inputs for a photo, a resume and a signature.
- **Marks section:** marks or grade plus the board for 10th, 12th and undergraduate studies, each with a board dropdown (for example CBSE, ICSE, SSLC, PUC, VTU).
- **Skill section:** specialisation branch dropdown (CSE, IT, ECE, EEE, Civil, Mechanical), date of birth, and a year of passing date picker limited to 2022.
- **Technical skills:** checkboxes for C, C++, Java, SQL, Python and CNN, followed by Submit and Reset buttons.

## How it works

- Layout and styling come from `css/main.css` and `css/util.css`, with custom radio buttons and dropdowns styled in a `<style>` block in the page.
- Icon and text fonts (Font Awesome 4.7, Material Design Iconic Font, Josefin Sans, Source Sans Pro) are bundled under `fonts/`.
- Validation is plain JavaScript in the page head: it checks name length, age, email format and phone number, requires a branch and at least one skill, and shows `alert()` messages for the year of passing check.
- HTML attributes such as `required`, `pattern`, `maxlength`, `min` and `max` add browser-side checks.

## Tech

HTML5, CSS3, vanilla JavaScript. No build step.

## Run it

Open `site/Main/Index.html` directly in a browser, or serve the folder:

```bash
cd site/Main
python -m http.server 8000
```

Then visit `http://localhost:8000/Index.html`. The form does not submit anywhere; there is no backend.

## Project structure

```
site/Main/
├── Index.html       # The registration form, inline validation script and styles
├── css/             # main.css and util.css
├── fonts/           # Bundled icon and text fonts
├── images/icons/    # favicon
├── js/main.js       # jQuery form validation helpers (not linked from the page)
├── presi.PNG        # Banner image
└── debug.log        # Browser crash-report log, not part of the site
```

## Notes

- The page links stylesheets from a `vendor/` folder (Bootstrap, animate.css, select2 and others) that is not in the repository, so those requests fail and the layout relies on `css/main.css` only.
- `js/main.js` needs jQuery and is not loaded by the page.
- Some validation does not run as intended: the script reads element IDs (such as `user` and `emails`) that do not exist in the form, the form tag has duplicate `onsubmit` attributes, and the banner is referenced as `presi.png` while the file is `presi.PNG`, which breaks on case-sensitive hosts.
- This is student coursework and is kept as it was submitted, apart from moving it into `site/`.
- No license file is included.
