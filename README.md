# IRG Manager Feedback

An anonymous staff feedback form for annual manager performance reviews. One page, no
build step, no dependencies. Staff open it on their phone, write, and submit — nothing
to install and no account to create.

## Setup

### 1. Formspree — already connected

The page posts to `https://formspree.io/f/xljenzjk`. Responses land in that Formspree
dashboard and are emailed to the address on the account, with the subject line
"Manager feedback (anonymous)". Nothing else needs editing.

Two settings to check in Formspree before going live:

- **Turn reCAPTCHA off.** It's on by default and can block JavaScript submissions like
  this one.
- Confirm the notification email is the address you actually want these going to.

The free tier allows 50 submissions per month, which is plenty for one review cycle.

### 2. Publish it

1. Create a new repository on GitHub and upload `index.html` to it.
2. Go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. Wait a minute. Your form is live at `https://<your-username>.github.io/<repo-name>/`.

A public repository is fine — the page holds no responses and no personal data. If you'd
rather it not be public, GitHub Pages on a private repo requires a paid plan; Netlify Drop
(drag the folder onto netlify.com/drop) is a free alternative with no repo at all.

### 3. Get it in front of staff

Generate a QR code for the URL and post it in the back of house. For hourly staff, a
posted QR code does more for response rate than an email ever will. Leave it up for about
two weeks and mention it in a pre-shift meeting once or twice.

## Editing the form

Everything is in `index.html` and readable without knowing HTML:

- **Manager names** — search for `Julio Silva` and `Patrick Courson` and replace them.
  Each appears twice: once in the heading, once in the `name=` attribute that labels the
  response.
- **Adding a third manager** — copy one of the `<section class="block">` blocks, paste it
  below, and change the name, the `id`, and the `for=` that points at it (they must match).
- **Intro text** — the paragraph with `class="intro"`.

## Notes on anonymity

The form collects no name, email, or identifying field, and the page loads no analytics or
tracking. Two things are still worth knowing:

- Form services log basic delivery metadata (such as IP address) for spam filtering. Nobody
  at IRG sees it, but "anonymous" here means *not attributed*, not technically untraceable.
  The page's wording reflects that on purpose.
- With a small team, a specific story can identify its author no matter what the form
  promises. Summarize themes; don't pass verbatim comments to a manager.

## Reading the responses

Wait until you have at least four responses per manager before summarizing anything at that
level of detail — below that, a manager can usually work out who said what. Group comments
into recurring themes, note where several people independently said the same thing, and
bring the themes into the review conversation rather than the raw text.
