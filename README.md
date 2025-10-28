interns-dpcourse
Beginner's Guide: Build a Simple Website with HTML
Audience: absolute beginners (interns) who are starting from scratch.

Goal: by the end you'll have a simple, well-structured static website (HTML + a little CSS) and understand the basic workflow to edit, preview, and publish it.

1. What is a website — the big picture
A website is a collection of files (HTML, CSS, images, sometimes JavaScript) that a browser (Chrome, Firefox, Edge, Safari) reads and renders into pages. HTML defines the structure/content, CSS defines the look/style, and JavaScript adds behavior (we'll only touch HTML + a little CSS here).

2. Tools you'll need (free & simple)
Code editor (pick one): VS Code (recommended), Sublime Text, Atom, or even Notepad. VS Code has helpful features for beginners.
Web browser for previewing: Chrome or Firefox recommended.
A file system / folders: create a project folder on your computer, e.g. my-first-site/.
Optional (for publishing): a free GitHub account and Git installed, or you can use GitHub Desktop.
3. Project setup — create the folder and files
Create a folder named my-first-site and inside create these files:

my-first-site/
  index.html
  styles.css
  images/
index.html is the homepage file browsers load by default.
styles.css will contain styling.
images/ holds pictures used by the site.
4. First HTML file — minimal page
Create index.html and paste this exact content. Then open the file in your browser (double-click it).

<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My First Website</title>
    <link rel="stylesheet" href="styles.css">
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
What to notice:

<!doctype html> declares HTML5.
<head> contains metadata (title, charset, responsive viewport, link to CSS).
<body> contains the visible page content.
5. Basic HTML building blocks (tags you’ll use a lot)
Headings: <h1> to <h6>
Paragraph: <p>
Links: <a href="URL">text</a>
Images: <img src="images/photo.jpg" alt="Description"> (always set alt)
Lists: <ul> (unordered) and <ol> (ordered) with <li> items
Sections & layout: <header>, <nav>, <main>, <section>, <article>, <aside>, <footer>
Forms (basic): <form>, <input>, <label>, <button> — we’ll show a tiny example later.
6. Add some style — styles.css
Create styles.css and add this simple CSS. Save and refresh the browser to see the changes.

/* Basic reset-ish and fonts */
* { box-sizing: border-box; }
body { font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; line-height: 1.5; margin: 0; padding: 0; }

header { background: #f3f4f6; padding: 1rem; }
header h1 { margin: 0 0 0.25rem 0; }
nav a { text-decoration: none; margin-right: 0.5rem; }

main { padding: 1rem; }
section { margin-bottom: 1rem; }

footer { background: #111827; color: #fff; padding: 1rem; text-align: center; }

/* Small responsive layout */
@media (min-width: 700px) {
  main { max-width: 900px; margin: 0 auto; }
}
Tip: You can edit the CSS file (change colors, font sizes) and then refresh the browser to see immediate results.

7. Add an image and assets
Put an image into the images/ folder (e.g., images/profile.jpg).
Insert it into HTML like:
<img src="images/profile.jpg" alt="Profile picture" width="300">
Always include alt text for accessibility.

8. Tiny contact form (HTML only)
Add this inside <main> to practice forms. Note: to actually send submissions you need a server—this example only shows the structure.

<section id="contact-form">
  <h2>Send a message</h2>
  <form action="#" method="post">
    <label for="name">Name</label><br>
    <input id="name" name="name" type="text" required><br>

    <label for="email">Email</label><br>
    <input id="email" name="email" type="email" required><br>

    <label for="msg">Message</label><br>
    <textarea id="msg" name="message"></textarea><br>

    <button type="submit">Send</button>
  </form>
</section>
9. Semantic HTML & accessibility — good habits
Use headings in order: one <h1> per page for the main title.
Use alt on images.
Use <label for="..."> connected to inputs for screen readers.
Use meaningful link text (avoid "click here").
10. Layout basics — block vs inline, and a hint about Flexbox
HTML elements are either block (take full width, like <div>, <p>, <h1>) or inline (like <a>, <span>).
For layout, modern CSS uses Flexbox and Grid. A simple horizontal nav using flexbox:
nav { display: flex; gap: 1rem; align-items: center; }
11. Making the site responsive (mobile-friendly)
Important: include this in the <head> — we already added it in the example above.

<meta name="viewport" content="width=device-width, initial-scale=1">
Use relative widths (percentages, max-width) and media queries (like @media (min-width: 700px) { ... }) to adjust layout for larger screens.

12. Workflow: edit, preview, repeat
Open index.html in the browser. 2. Edit index.html or styles.css in your editor. 3. Save. 4. Refresh the browser. Repeat.
Advanced: use the VS Code Live Server extension to auto-reload the page when files change.

13. Quick local checklist (what to test)
 Page opens in browser and shows content.
 Navigation links work (anchor links or other pages).
 Images display and have alt text.
 Styles from styles.css are applied.
 Page looks okay on narrow screens (shrink your browser width).
14. Publish your site — quick GitHub Pages flow (one simple option)
If you want to publish: create a free GitHub account, create a repository called my-first-site, push your files to the repo, then enable GitHub Pages in repository settings (choose main branch / / root). GitHub Pages will serve your index.html at https://username.github.io/my-first-site/.

Basic commands (git must be installed) run in your my-first-site folder:

git init
git add .
git commit -m "Initial site"
# create repo on GitHub (via website) and follow instructions to add remote, then:
git remote add origin git@github.com:your-username/my-first-site.git
git branch -M main
git push -u origin main
(Or use GitHub Desktop to avoid the command line if you prefer.)

15. Next learning steps (suggested roadmap)
Learn more HTML tags: <table>, <figure>, <blockquote>.
Learn CSS layout: Flexbox, Grid.
Learn responsive patterns and accessibility guidelines.
Learn the basics of JavaScript to make pages interactive.
Learn version control (git) and automated deployment.
16. Exercises for interns (small tasks with increasing difficulty)
HTML basics: Edit index.html — change the text in headings and paragraphs. Add a new list item.
Images: Add two images, provide alt text, and resize them with CSS.
Styling: Change the header background color and make links change color on hover using a:hover.
Layout: Make the nav horizontal using display:flex.
New page: Create about.html, link it from the navigation, and ensure the link works.
Publish: Push to GitHub Pages and share the site URL.
17. Common beginner mistakes & how to fix them
Nothing shows up — are you opening the index.html file? Check for typos in filenames.
CSS not applied — ensure the <link rel="stylesheet" href="styles.css"> path is correct and cached; try hard-refresh (Ctrl/Cmd+Shift+R).
Image broken — check src path and file extension (jpg vs png). Case-sensitive file systems care about uppercase/lowercase.
Form doesn't send — static HTML forms need a backend to process submissions; for testing use action="#" or use a third-party form service.
18. Handy sample: full index.html (copy-paste ready)
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My First Website</title>
    <link rel="stylesheet" href="styles.css">
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
        <p>This is a simple website built with HTML and CSS. Start editing to make it your own!</p>
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
          <label for="name">Name</label><br>
          <input id="name" name="name" type="text" required><br>

          <label for="email">Email</label><br>
          <input id="email" name="email" type="email" required><br>

          <label for="msg">Message</label><br>
          <textarea id="msg" name="message"></textarea><br>

          <button type="submit">Send</button>
        </form>
      </section>

    </main>

    <footer id="contact">
      <p>Contact: <a href="mailto:you@example.com">you@example.com</a></p>
    </footer>
  </body>
</html>
19. Quick reference — useful snippets
Link to CSS

<link rel="stylesheet" href="styles.css">
Add an image

<img src="images/pic.jpg" alt="Description" width="400">
Simple flex container

.container { display: flex; gap: 1rem; }
20. Where to find more learning resources
MDN Web Docs (HTML & CSS) — clear reference docs.
FreeCodeCamp — tutorials and exercises.
W3Schools — quick examples (use carefully as a quick reference).
