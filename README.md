# IRG Manager Feedback

An anonymous staff feedback form for annual manager performance reviews. One page, no
build step, no dependencies. Staff open it on their phone, write, and submit — nothing
to install and no account to create.

Current managers on the form, listed alphabetically by last name:
Blake Bilodeau, Mateo Calderon, Cristian Diaz, Kevin Kok, Mark Ramos, James Riojas,
Julio Silva.

## Setup

### 1. Formspree — already connected

The page posts to `https://formspree.io/f/xljenzjk`. Responses land in that Formspree
dashboard and are emailed to the address on the account, with the subject line
"Manager feedback (anonymous)". Nothing else needs editing.

Two settings to check in Formspree before going live:

- **Turn reCAPTCHA off.** It's on by default and can block JavaScript submissions like
  this one.
- Confirm the notification email is the address you actually want these going to.

The free tier allows 50 submissions per month. With seven managers on one form, each
staff member still counts as a single submission.

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

Everything is in `index.html` and readable without knowing HTML.

**To rename a manager**, search for their full name. It appears three times in their
block — the `for=`, the heading text, and the `name=` that labels the response in
Formspree — plus their first name in the placeholder. Change all of them.

**To remove a manager**, delete their whole `<section class="block">` … `</section>` block.

**To add one**, copy an existing block, paste it in, and change the name, the `id`, and the
`for=` that points at it. The `id` and the `for=` must match each other, and should be
something short and unique like the person's last name.

**Intro text** is the paragraph with `class="intro"`.

## Notes on anonymity

The form collects no name, email, or identifying field, and the page loads no analytics or
tracking. Two things are still worth knowing:

- Formspree logs basic delivery metadata (such as IP address) for spam filtering. Nobody
  at IRG sees it, but "anonymous" here means *not attributed*, not technically untraceable.
  The page's wording reflects that on purpose.
- With a small team, a specific story can identify its author no matter what the form
  promises. Summarize themes; don't pass verbatim comments to a manager.

## Reading the responses

Blank boxes come through empty, so you can see at a glance which managers each person
chose to comment on.

Wait until you have at least four responses about a given manager before summarizing
anything at a detailed level — below that, they can usually work out who said what. Group
comments into recurring themes, note where several people independently said the same
thing, and bring the themes into the review conversation rather than the raw text.
