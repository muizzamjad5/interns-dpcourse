# Beginner's Guide: Build a Simple Website with HTML

**Audience:** absolute beginners (interns) starting from zero.

**Goal:** by the end of this guide you will:

* Have a simple, working website made with HTML + a little CSS.
* Know how to edit it, preview it, and publish it online.

We'll go step by step. You can follow this like a checklist.

---

## 0. Before we start: what you'll actually build

You're going to build a tiny personal site that has:

* A header with navigation links (Home / About / Contact)
* Some content sections
* A contact form (structure only)
* Basic responsive styling so it doesn't look awful on mobile

You'll edit two files:

* `index.html` (the content and structure)
* `styles.css` (the styling)

At the end, you'll optionally put it on the internet using GitHub Pages.

---

## 1. What is a website? (The big picture)

A website is just a collection of files that live in a folder.

Your browser (Chrome, Firefox, Edge, Safari) opens those files and renders them.

The main file types you'll see:

* **HTML** (`.html`) → the *structure* and *content* of the page (text, images, links, headings, etc.)
* **CSS** (`.css`) → the *appearance* of the page (colors, fonts, layout)
* **Images** (`.jpg`, `.png`, `.svg`, etc.) → visuals used on your page
* **JavaScript** (`.js`) → interactivity / behavior (menus that open, buttons that do things). We won't cover JS here.

For this guide, we're focusing on **HTML + CSS only**.

---

## 2. Tools you'll need (all free)

You do **not** need anything fancy.

### 2.1 Code editor (pick one)

* **VS Code (recommended)** → helpful for beginners (syntax highlighting, auto-complete, extensions)
* Sublime Text
* Atom
* As a last resort: Notepad / TextEdit (works, but not fun)

### 2.2 A browser to preview your page

* Chrome or Firefox are great
* You will literally double-click your `index.html` file to open it in the browser

### 2.3 A project folder in your computer

* This is where your site's files will live

### 2.4 Optional (for publishing to the internet)

* A free GitHub account
* Git installed, or GitHub Desktop if you don't like the command line

---

## 3. Project setup — create your folder and files

Create a folder called `my-first-site/`.

Inside it, create:

```text
my-first-site/
  index.html
  styles.css
  images/
```

What each one is for:

* `index.html` → the main page (browsers look for this by default)
* `styles.css` → the styles for the whole site
* `images/` → put your pictures in here

> ✅ Pro tip: keep filenames lowercase, no spaces. Example: `profile.jpg`, not `My Profile Pic.JPG`.

---

## 4. Your first HTML page

Open `index.html` in your editor and paste this EXACT code:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>My First Website</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <h1>Welcome to My First Website</h1>
      <nav>
        <a href="#">Home</a> |
        <a href="#about">About</a> |
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main>
      <section id="about">
        <h2>About this site</h2>
        <p>This is a simple website built with HTML and a little CSS.</p>
      </section>

      <section>
        <h2>My Skills (example)</h2>
        <ul>
          <li>HTML</li>
          <li>CSS</li>
          <li>Learning JavaScript</li>
        </ul>
      </section>
    </main>

    <footer id="contact">
      <p>Contact: <a href="mailto:you@example.com">you@example.com</a></p>
    </footer>
  </body>
</html>
```

Now **save the file**, then open it:

1. Go to your folder.
2. Double-click `index.html`.
3. Your browser should open and show your first website 🎉

### 4.1 What to notice in that HTML

* `<!doctype html>` → tells the browser this is an HTML5 document.
* `<head>...</head>` → info *about* the page (title, character set, responsive settings, link to CSS). This stuff isn't directly shown on the page.
* `<body>...</body>` → the actual visible content.
* `<header>`, `<main>`, `<footer>` → semantic layout sections.
* `<nav>` → navigation links.
* `<section>` → logical content blocks.

---

## 5. The essential HTML building blocks

You'll reuse these tags over and over:

* **Headings:**

  ```html
  <h1>Main page title</h1>
  <h2>Subheading</h2>
  <h3>Smaller section heading</h3>
  ```

  Use `<h1>` once per page for the main title, then `<h2>`, `<h3>`, etc. in order.

* **Paragraph:**

  ```html
  <p>This is a paragraph of text.</p>
  ```

* **Link:**

  ```html
  <a href="https://example.com">Visit Example</a>
  ```

* **Image:**

  ```html
  <img src="images/photo.jpg" alt="Description of the photo" />
  ```

  * `alt` is important for accessibility and screen readers.

* **List:**

  ```html
  <ul>
    <li>Item one</li>
    <li>Item two</li>
  </ul>
  ```

  Use `<ul>` for an unordered (bulleted) list, `<ol>` for a numbered list.

* **Layout / semantic elements:**

  ```html
  <header> ... </header>
  <nav> ... </nav>
  <main> ... </main>
  <section> ... </section>
  <article> ... </article>
  <aside> ... </aside>
  <footer> ... </footer>
  ```

  These help with structure and accessibility.

* **Basic form elements:**

  ```html
  <form>
    <label>Name <input type="text" /></label>
    <button>Send</button>
  </form>
  ```

---

## 6. Add some style (create `styles.css`)

Now open `styles.css` and paste this:

```css
/* --- Basic reset & font setup --- */
* {
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  line-height: 1.5;
  margin: 0;
  padding: 0;
}

/* --- Header --- */
header {
  background: #f3f4f6;
  padding: 1rem;
}

header h1 {
  margin: 0 0 0.25rem 0;
}

nav a {
  text-decoration: none;
  margin-right: 0.5rem;
  color: inherit;
}

nav a:hover {
  text-decoration: underline;
}

/* --- Main content area --- */
main {
  padding: 1rem;
}

section {
  margin-bottom: 1rem;
}

/* --- Footer --- */
footer {
  background: #111827;
  color: #fff;
  padding: 1rem;
  text-align: center;
}

footer a {
  color: #fff;
  text-decoration: underline;
}

/* --- Small responsive layout tweak --- */
@media (min-width: 700px) {
  main {
    max-width: 900px;
    margin: 0 auto;
  }
}
```

Now save `styles.css`, go back to your browser, and refresh the page.

You should see:

* Softer background on the header
* Better font
* Dark footer
* Content not stretched full-width on larger screens

> ✅ Experiment: change `background: #f3f4f6;` to a different color, save, refresh.

---

## 7. Add an image to the page

1. Put an image file in the `images/` folder (example: `images/profile.jpg`).
2. In your `index.html`, inside `<main>`, add something like this:

```html
<img src="images/profile.jpg" alt="Profile picture" width="300" />
```

Notes:

* `width="300"` scales the image (the browser auto-calculates the height to keep proportions)
* `alt="..."` helps people using screen readers and also helps SEO

If the image doesn't show up:

* Check the filename (`profile.jpg` vs `Profile.JPG` → not the same on some systems)
* Check that it's really inside the `images/` folder

---

## 8. Add a tiny contact form (HTML only)

We'll add a simple form so the page feels more “real.”

⚠️ This form will **not send email** by itself. You need a backend/server or a service for that. But it's important to learn the structure.

Add this **inside `<main>`** in `index.html`:

```html
<section id="contact-form">
  <h2>Send a message</h2>
  <form action="#" method="post">
    <label for="name">Name</label><br />
    <input id="name" name="name" type="text" required /><br /><br />

    <label for="email">Email</label><br />
    <input id="email" name="email" type="email" required /><br /><br />

    <label for="msg">Message</label><br />
    <textarea id="msg" name="message"></textarea><br /><br />

    <button type="submit">Send</button>
  </form>
</section>
```

Why it's good:

* `<label for="name">` matches `id="name"`, which helps screen readers know which label belongs to which input.
* `required` means the browser will not let you submit empty fields.

---

## 9. Accessibility & semantic HTML (good habits early)

Get these habits in now and people will think you already know what you're doing:

* Use **one `<h1>` per page** for the main title, then `<h2>`, `<h3>`, etc. in logical order.
* Always add `alt` text to images, unless they are purely decorative. Example: `alt="Portrait of Alex smiling"`.
* Use `<label>` with `for` for every input in your forms.
* Use meaningful link text. Good: `Contact me`. Bad: `click here`.
* Use real semantic elements like `<header>`, `<main>`, `<footer>` instead of just a bunch of `<div>`s. This helps accessibility tools and search engines understand your page.

---

## 10. Layout basics (block vs inline + a hint of Flexbox)

HTML elements are roughly two types:

* **Block elements** (like `<div>`, `<p>`, `<h1>`, `<section>`) → take up the full width available and start on a new line.
* **Inline elements** (like `<a>`, `<span>`, `<strong>`) → only take up as much width as needed and sit in the same line.

Modern layouts use **Flexbox** and **Grid** (we'll just peek at Flexbox).

This is how you'd make the nav links sit horizontally with spacing, using Flexbox:

```css
nav {
  display: flex;
  gap: 1rem;
  align-items: center;
}
```

You can add that to `styles.css` to replace the simple `nav` styling.

---

## 11. Mobile-friendly design (responsiveness)

Phones are narrow. Laptops are wide. Your site should adapt.

### 11.1 The viewport meta tag (super important)

In your `<head>` we already included:

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

This tells the browser: “don't zoom out automatically on mobile — render this at the device width.” Without it, your site looks tiny on phones.

### 11.2 Media queries in CSS

In `styles.css` you saw this:

```css
@media (min-width: 700px) {
  main {
    max-width: 900px;
    margin: 0 auto;
  }
}
```

This means:

* On screens **700px wide or larger** (like laptops), limit the text column width and center it.
* On smaller screens (phones), let it be full width.

This is how you create responsive layouts.

---

## 12. Your workflow (the normal loop of web dev)

This is what real developers do all day:

1. **Open the site in a browser** by opening `index.html`.
2. **Edit code** in VS Code.
3. **Save** your file.
4. **Refresh the browser** (Ctrl/Cmd + R) and check.
5. Repeat.

### 12.1 Bonus: "Live Server" in VS Code

You can install the "Live Server" extension in VS Code. When you run it, it auto-reloads your browser tab whenever you save.

This saves a lot of time.

---

## 13. Quick test checklist before you ship it

Open your page and check:

* [ ] Page opens in the browser with no blank screen / no scary error
* [ ] Navigation links work (they scroll to the right section or go to the right page)
* [ ] Images actually appear and have good `alt` text
* [ ] Styles from `styles.css` are clearly applied
* [ ] Page text is readable on a phone-sized width
* [ ] Footer looks okay and text is readable

If all that is true, nice.

---

## 14. Put your site on the internet using GitHub Pages (optional)

GitHub Pages is a free way to publish static sites (HTML/CSS/JS only — which is exactly what you're building).

### 14.1 Create a GitHub repo

1. Make a GitHub account (free).
2. In your computer, open a terminal / command prompt and go into your project folder:

   ```bash
   cd path/to/my-first-site
   ```
3. Run these commands:

   ```bash
   git init
   git add .
   git commit -m "Initial site"
   ```

### 14.2 Connect to GitHub

1. Create a new repo on GitHub called `my-first-site` (do this on the GitHub website).
2. Follow GitHub's instructions to connect your local folder to that repo. It will look something like:

   ```bash
   git remote add origin git@github.com:your-username/my-first-site.git
   git branch -M main
   git push -u origin main
   ```

Now your code is on GitHub.

### 14.3 Turn on GitHub Pages

1. Go to your repository's **Settings** on GitHub.
2. Look for **Pages** (sometimes under "Code and automation" → "Pages").
3. Choose:

   * Source / Branch: `main`
   * Directory / Folder: `/ (root)`
4. Save.

GitHub Pages will publish your `index.html` at:

```text
https://your-username.github.io/my-first-site/
```

Share that link with people. You're live.

> No server. No backend. 100% free. Perfect for portfolios and small info pages.

If you hate the command line, you can use **GitHub Desktop** — it's a GUI that does `commit` and `push` for you.

---

## 15. Where to go next (your growth path)

To level up after this:

1. **More HTML elements**

   * `<table>` for data
   * `<figure>` + `<figcaption>` for images with captions
   * `<blockquote>` for quotes

2. **More CSS layout**

   * Flexbox
   * CSS Grid (2D layouts, galleries, dashboards)

3. **Responsive design & accessibility**

   * Better mobile layouts
   * High contrast / readable fonts
   * Keyboard navigation

4. **JavaScript basics**

   * Add interactivity (toggle menus, light/dark mode buttons, etc.)

5. **Git & deployment**

   * Branches
   * Pull requests
   * Automated deploys

---

## 16. Exercises for interns (do these!)

Do these in order. Do not skip.

1. **HTML basics**

   * Edit the text in `<h1>` and `<p>` in `index.html` so it describes you.
   * Add another `<li>` to the list under "My Skills" or "Things I am learning".

2. **Images**

   * Add two images to the page, each with meaningful `alt` text.
   * Control their size with `width="300"` or via CSS.

3. **Styling tweak**

   * Change the header background color in `styles.css`.
   * Add a hover effect on links:

     ```css
     nav a:hover {
       color: red;
     }
     ```

4. **Layout with Flexbox**

   * Update the `nav` styles in `styles.css` to:

     ```css
     nav {
       display: flex;
       gap: 1rem;
       align-items: center;
     }
     ```
   * Refresh and confirm the links sit in a neat row.

5. **New page**

   * Create a new file called `about.html`.
   * Copy the structure of `index.html` into it.
   * Change the main content so it talks about you / your project / your team.
   * In `index.html`, update your nav:

     ```html
     <nav>
       <a href="index.html">Home</a>
       <a href="about.html">About</a>
       <a href="#contact">Contact</a>
     </nav>
     ```
   * Click the About link in the browser and make sure it loads.

6. **Publish** (stretch goal)

   * Push to GitHub Pages.
   * Send the live URL to your mentor.

---

## 17. Common beginner mistakes (and fixes)

### 17.1 "Nothing shows up"

* Are you actually *opening* `index.html` in a browser?
* Did you maybe rename it `index.html.txt` by accident? (Windows sometimes hides extensions.)
* Did you forget to save?

### 17.2 "My CSS isn't working"

* Check this line in your `<head>`:

  ```html
  <link rel="stylesheet" href="styles.css" />
  ```
* Is the filename spelled exactly `styles.css`?
* Try a hard refresh (Ctrl/Cmd + Shift + R).

### 17.3 "My image is broken (little broken-image icon)"

* Is the path correct? Example: `images/profile.jpg`
* Is the file actually in the `images/` folder?
* Is it `.jpg` or `.png`? Spelling matters. Case matters on some systems.

### 17.4 "The form doesn't send me email"

* Correct. Plain HTML cannot send email by itself.
* For now, keep `action="#"` so the page doesn't try to navigate.
* Later you can connect it to:

  * A backend you build
  * A form service (Formspree, Netlify Forms, etc.)

---

## 18. Full `index.html` (copy-paste ready)

This is a slightly more complete version with nav links, sections, and a contact form.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>My First Website</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <h1>Welcome to My First Website</h1>
      <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main>
      <section id="about">
        <h2>About this site</h2>
        <p>
          This is a simple website built with HTML and CSS. Start editing to make it your own!
        </p>
      </section>

      <section>
        <h2>Things I am learning</h2>
        <ul>
          <li>HTML &amp; semantic structure</li>
          <li>CSS basics</li>
          <li>Responsive design</li>
        </ul>
      </section>

      <section id="contact-form">
        <h2>Contact</h2>
        <form action="#" method="post">
          <label for="name">Name</label><br />
          <input id="name" name="name" type="text" required /><br /><br />

          <label for="email">Email</label><br />
          <input id="email" name="email" type="email" required /><br /><br />

          <label for="msg">Message</label><br />
          <textarea id="msg" name="message"></textarea><br /><br />

          <button type="submit">Send</button>
        </form>
      </section>
    </main>

    <footer id="contact">
      <p>
        Contact:
        <a href="mailto:you@example.com">you@example.com</a>
      </p>
    </footer>
  </body>
</html>
```

---

## 19. Quick reference snippets

You don't have to memorize anything. Copy/paste these.

**Link to your CSS file (goes in `<head>`):**

```html
<link rel="stylesheet" href="styles.css" />
```

**Add an image:**

```html
<img src="images/pic.jpg" alt="Description of the image" width="400" />
```

**Simple Flexbox row layout in CSS:**

```css
.container {
  display: flex;
  gap: 1rem;
}
```

**Centered, max-width content for large screens:**

```css
main {
  max-width: 900px;
  margin: 0 auto;
  padding: 1rem;
}
```

---

## 20. Learning resources

When you're stuck or curious, these are reliable places to read more:

* **MDN Web Docs (Mozilla Developer Network)**

  * The most accurate reference for HTML, CSS, and JavaScript.
  * Great for "What does this tag do?"

* **freeCodeCamp**

  * Step-by-step tutorials and practice challenges.
  * Good if you like guided learning.

* **W3Schools**

  * Fast, copy/paste-friendly examples.
  * Use for quick reminders / syntax checks.

---


