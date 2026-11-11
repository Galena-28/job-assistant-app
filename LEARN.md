# Stage 1 — Learn the basics (plain-English guide)

This folder holds your first practice page for the Job Application Assistant App.
It is deliberately tiny, so you can see how every part works before the app grows.

## What's in the folder

| File | What it is |
|---|---|
| `index.html` | The practice page itself. Open it in any browser. |
| `LEARN.md` | This guide. |
| `PROGRESS.md` | Your roadmap checklist (Stage 1 to Stage 8). |

## What the page does

1. You paste a job advert into the big box.
2. You type your skills, separated by commas.
3. You press **Check my match**.
4. The page shows a score out of 10, the skills the advert mentions (blue), and the ones it doesn't (orange).

It doesn't use AI yet. It just looks for your exact words in the advert. In Stage 2 the Claude API will replace this simple word check with a real reading of the advert.

## The three parts of every web page

Think of a shop:

- **HTML is the shelves and products**: the heading, the text boxes, the button. In `index.html`, it's everything inside `<body>`.
- **CSS is the paint and decoration**: colors, spacing, rounded corners, dark mode. It's inside `<style>`.
- **JavaScript is the shop assistant**: it waits for you to press the button, does the counting, and shows the answer. It's inside `<script>`.

Each section of `index.html` has comments (lines starting with `<!--`, `/*` or `//`) that say what it does. The browser ignores comments. They're notes for people.

## Step by step: what happens when you press the button

1. **Find the parts.** The script grabs the advert box, the skills box and the result box by their `id` names.
2. **Listen for a click.** `addEventListener("click", ...)` means "when this button is clicked, run the following steps."
3. **Clean the input.** It splits your skills at each comma, trims spaces and drops empty ones.
4. **Check for missing input.** If either box is empty, it shows a message and stops, the same "ask instead of guessing" rule the real app will follow.
5. **Compare.** Each skill is sorted into "found" or "missing" by checking whether the advert contains it.
6. **Score.** Found skills divided by all skills, times 10, rounded to a whole number.
7. **Show.** The result box is filled in and un-hidden.

## Design choices that match your plan

- **Works on phones.** The `viewport` line plus 16px edge spacing make it fit small screens.
- **Light and fast.** There are no images, fonts or outside files, which suits users on limited mobile data.
- **Private.** Nothing is sent anywhere. Everything happens in your browser.
- **Safe.** Typed text is always shown as plain text, never run as code (`escapeText`).

## Small exercises to try (ask Claude Code for each one)

Do these one at a time, as your plan's tips suggest:

1. ✅ "Change the green color to blue." *(Learn: CSS variables in `:root`)*
2. ✅ "Add a Clear button that empties both boxes." *(Learn: a second button and click listener)*
3. ✅ "Remember my skills when I reload the page." *(Learn: saving in the browser)*
4. "Show a message like 'Strong match' when the score is 7 or more." *(Learn: if/else)*

After each one works, ask Claude to **save a version** (a git commit), so you can always go back.

## Saving versions (git) in plain words

`git` is a "save game" system for code. Each **commit** is a snapshot with a short note.
If something breaks, you can return to any earlier snapshot. This folder already has its first snapshot.

## Stage 1 is done when you can

- [ ] Open the page and use it on your phone and computer
- [ ] Point to the HTML, CSS and JavaScript parts and say what each does
- [ ] Complete at least two of the exercises above with Claude Code
- [ ] Save a version after each one
