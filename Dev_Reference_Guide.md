# Isabel's Web Development Reference Guide
*GitHub · Firebase · Frontend · App Architecture*

*A living document — add to this as you learn. Started May 2026 during the World Cup 2026 Pool project.*

---

## What Is GitHub, Really?

GitHub is two things in one:

1. **Git** — a system that tracks every change ever made to your code (like "track changes" in Word, but for code, and it never forgets anything)
2. **GitHub** — a website that hosts your Git history online so you can access it anywhere, share it, and collaborate

**The core mental model:** Every project lives in a **repository** (repo). A repo is like a folder that remembers its entire history — every version of every file, forever.

---

## The Repository Page — Every Element Explained

This is what you see when you open `github.com/isa809/wc2026pool`.

---

### Top Navigation Bar

```
isa809 / wc2026pool
```
- **isa809** = your GitHub username (the owner)
- **wc2026pool** = the repository name
- Together this is the "address" of your project on GitHub

```
Code | Issues | Pull requests | Actions | Projects | Wiki | Security | Insights | Settings
```

| Tab | What it's for | When you use it |
|---|---|---|
| **Code** | View and edit files | Most of the time — this is home base |
| **Issues** | Bug reports and feature requests | Tracking what needs to be done |
| **Pull requests** | Proposed changes for review | When collaborating with others |
| **Actions** | Automated workflows (CI/CD) | Auto-deploy when you push code |
| **Projects** | Kanban board / task management | Like Trello but inside GitHub |
| **Wiki** | Documentation pages | Writing guides for your project |
| **Security** | Vulnerability alerts | When GitHub detects security issues |
| **Insights** | Traffic, contributors, activity | Seeing who uses your repo |
| **Settings** | Repo configuration | GitHub Pages, rename, delete, etc. |

---

### Repository Header

```
wc2026pool  [Public]
```
- **Public** = anyone on the internet can see this code (required for free GitHub Pages)
- **Private** = only you (and people you invite) can see it

```
Pin | Watch 0 | Fork 0 | Star 0
```

| Button | What it does |
|---|---|
| **Pin** | Pin this repo to your GitHub profile so visitors see it first |
| **Watch** | Get email notifications when anyone makes changes |
| **Fork** | Make your own copy of someone else's repo to modify freely |
| **Star** | Like a bookmark — shows you appreciate the project, adds to your starred list |

> **Fork vs Star:** Star = bookmark. Fork = copy the whole project into your own account so you can change it.

---

### Branch Area

```
main ▼  |  1 Branch  |  0 Tags
```

**Branch** = a parallel version of your code. Think of it like a copy of your document where you can experiment without touching the original.

| Concept | Analogy | When to use |
|---|---|---|
| **main** | The "official" published version | What users see when the site is live |
| **Branch** | A draft / scratchpad | When testing a new feature |
| **Merge** | Accepting the draft into official | When your feature is ready |

Right now you only have `main`. That's fine for a solo project — you'll only need branches when you want to experiment without breaking the live app.

**Tags** = labels on specific commits like "v1.0", "launch", etc. Used for marking release versions.

---

### File Area

```
isa809   Initial commit   ee7e0a4 · now   1 Commit
```

| Element | What it means |
|---|---|
| **isa809** | Who made the last change |
| **Initial commit** | The commit message (description of what changed) |
| **ee7e0a4** | The commit ID — a unique fingerprint for that exact version |
| **now** | When the commit happened |
| **1 Commit** | Total number of changes recorded in history |

---

### The Commit — Most Important Concept in Git

A **commit** is a saved snapshot of your code at a specific moment. Every time you make changes and want to save them, you commit.

Think of commits like **save points in a video game**. You can always go back to any save point.

```
Good commit messages (be specific):
✅ "Add Firebase connection to saveST function"
✅ "Fix final pick [object Object] bug"
✅ "Update scoring from 200 to 225 points"

Bad commit messages (too vague):
❌ "update"
❌ "fix stuff"
❌ "changes"
```

Why does the message matter? When something breaks 3 months from now and you need to find when it broke, good messages let you scan history in seconds.

---

### Code Button (Green)

```
<> Code ▼
```

Clicking this gives you options to download or copy the code:

| Option | What it does |
|---|---|
| **HTTPS URL** | The address you use to "clone" (download) the repo via terminal |
| **Download ZIP** | Just download all files as a zip — no Git, no history |
| **Open with GitHub Desktop** | Use the GitHub desktop app instead of terminal |
| **Open with Codespaces** | Open a full VS Code editor in the browser |

For now, **Download ZIP** is all you need when you want to get your files back locally.

---

### About Panel (Right Side)

```
World Cup 2026 Prediction Pool
□ Readme
⚡ Activity
☆ 0 stars
👁 0 watching
⑂ 0 forks
```

| Element | What it means |
|---|---|
| **Description** | The one-line summary you set when creating the repo |
| **Readme** | Quick link to your README.md file |
| **Activity** | Recent commits and events |
| **Stars** | How many people starred it |
| **Watching** | How many people get notifications |
| **Forks** | How many people copied it to their own account |

---

### README.md

The file at the bottom of your repo page that renders as formatted text. It's the "front door" of your project — the first thing anyone sees.

**Convention:** Every repo should have a README that explains:
- What the project does
- How to run it
- Any important notes

You currently have a basic one. We'll update it once the app is live.

---

## Core Git Concepts You'll Use

### The Three Stages of a File Change

```
1. You edit a file     →  "modified" (only on your computer)
2. You "stage" it      →  "staged" (marked for the next commit)
3. You "commit" it     →  "committed" (saved to Git history)
4. You "push" it       →  "pushed" (uploaded to GitHub)
```

On GitHub's website, steps 2-4 happen automatically when you click "Commit changes."

---

### The Most Common Things You'll Do

| Action | What it means | On GitHub website |
|---|---|---|
| **Commit** | Save a snapshot of changes | Edit file → scroll down → "Commit changes" |
| **Push** | Upload commits to GitHub | Happens automatically on the website |
| **Pull** | Download latest changes | Needed when using local tools |
| **Clone** | Download entire repo | Green Code button → copy URL |
| **Fork** | Copy someone's repo | Fork button on their repo |
| **Branch** | Create a parallel version | Branch dropdown → New branch |
| **Merge** | Combine a branch into main | Pull request → Merge |

---

## GitHub Pages — How Your App Gets Hosted

GitHub Pages turns your repository into a website for free.

**How it works:**
1. You enable Pages in Settings → Pages
2. GitHub looks at your `main` branch for an `index.html` file
3. It serves that file at `https://USERNAME.github.io/REPONAME`
4. Every time you commit a new version, the site updates automatically (takes ~2 min)

**What it can serve:** HTML, CSS, JavaScript — anything a browser can run directly.
**What it cannot do:** Run server-side code (Node.js, Python, etc.), connect to databases.

**Your URL will be:** `https://isa809.github.io/wc2026pool`

---

## The Workflow You'll Use Most

For your single-file apps (like WC2026Pool and your budgeting app):

```
1. Make changes to your HTML file locally (or in Claude)
2. Go to your repo on GitHub
3. Click the file → click pencil ✏️ to edit
   OR click "Add file → Upload files" to replace
4. Write a meaningful commit message
5. Click "Commit changes"
6. Wait ~2 minutes
7. Your live site is updated
```

That's it. No terminal required.

---

## Transferable Concepts for Your Budgeting App

Everything you're learning here applies directly:

| WC2026 Pool | Budgeting App | Concept |
|---|---|---|
| `WorldCup2026Pool.html` | `budget.html` | Single-file frontend app |
| `ST` object | Budget state object | Global app state |
| `saveST()` | `saveBudget()` | Persistence layer |
| `localStorage` → Firebase | Same path | Moving from local to shared |
| `render()` → `setTab()` | Same pattern | Re-render on state change |
| Admin PIN | Password protection | Simple auth |
| Group picks scoring | Budget category tracking | Data modeling |

**Key insight:** The architecture of your WC2026 app — one state object, one render function, save on every change, tabs for different views — is a legitimate frontend pattern used in production apps. React, Vue, and Angular are just fancier versions of exactly what you built.

---

## Glossary

| Term | Plain English |
|---|---|
| **Repository (repo)** | A project folder that remembers all its history |
| **Commit** | A saved snapshot with a description |
| **Branch** | A parallel copy of the code for experimenting |
| **Main** | The primary/official branch |
| **Merge** | Combining a branch back into main |
| **Push** | Uploading your commits to GitHub |
| **Pull** | Downloading the latest commits from GitHub |
| **Clone** | Downloading an entire repo to your computer |
| **Fork** | Copying someone else's repo to your account |
| **README** | The "front door" document of a repo |
| **GitHub Pages** | Free static website hosting from a repo |
| **CI/CD** | Automated testing and deployment pipelines |
| **Open source** | Code anyone can see, use, and contribute to |
| **Issue** | A reported bug or feature request |
| **Pull Request (PR)** | A proposed change waiting for review |
| **Markdown (.md)** | Simple formatting syntax — `**bold**`, `# heading`, etc. |
| **Static site** | A website with no server — just HTML/CSS/JS files |
| **Backend** | Server-side code that handles data and logic |
| **Frontend** | Browser-side code that users see and interact with |
| **API** | A way for two pieces of software to talk to each other |
| **Firebase** | Google's hosted backend — database + auth + hosting |
| **localStorage** | Browser's built-in notepad — only visible to that browser |

---

## Next Steps to Learn More

**Free resources (in order of usefulness):**
1. **GitHub's own "Hello World" guide** — github.com/skills — interactive, takes 1 hour
2. **The Odin Project** — theodinproject.com — free full-stack curriculum, starts from zero
3. **MDN Web Docs** — developer.mozilla.org — the authoritative HTML/CSS/JS reference
4. **Firebase documentation** — firebase.google.com/docs — especially "Get Started" for Realtime Database

**What to build next to reinforce this:**
- The zero-sum budgeting app (you already started with base44 — port it to a single HTML file)
- Add Firebase to both apps in one session (same code, same concepts)
- Try the multi-pool feature (introduces URL routing and data scoping)

---

---

## What "Commit Changes" Means and Does

When you upload a file to GitHub and click **Commit changes**, Git does three things simultaneously:

**1. Saves a permanent snapshot**
It photographs every file in your repo at that exact moment and stores it forever. Even if you delete the file tomorrow, that snapshot still exists in history.

**2. Records who did it and when**
```
Author:  isa809
Time:    [timestamp]
Message: "Add WorldCup2026Pool.html"  ← whatever you typed
```

**3. Moves the "current version" pointer forward**
```
Before:                     After:

[Initial commit]            [Initial commit] → [Add WC2026 file]
    ↑                                               ↑
  "main"                                          "main"
```
The label `main` always points to the most recent commit. It moved forward.

---

### The Filing Cabinet Metaphor

Imagine your repo is a filing cabinet with a camera above it.

**Before you uploaded:**
```
Filing cabinet contains:
📄 README.md
```

**You uploaded the HTML file and clicked Commit changes:**
```
Camera took a photo of the cabinet:
📷 Snapshot #2 — "Added WorldCup2026Pool.html"
    📄 README.md
    📄 WorldCup2026Pool.html

This photo is stored permanently. You can never lose it.
```

**If you upload a new version tomorrow and commit again:**
```
📷 Snapshot #3 — "Fixed scoring bug"
    📄 README.md
    📄 WorldCup2026Pool.html  ← new version

📷 Snapshot #2 — "Added WorldCup2026Pool.html"  ← still exists
    📄 README.md
    📄 WorldCup2026Pool.html  ← old version, still accessible
```

You can click on Snapshot #2 at any time and get the old file back. **Nothing is ever truly deleted.**

---

### The Two Fields in the Commit Dialog

When you click Commit changes a small form appears:

```
┌─────────────────────────────────────┐
│ Commit message (required)           │
│ ┌─────────────────────────────────┐ │
│ │ Add WorldCup2026Pool.html       │ │  ← short summary
│ └─────────────────────────────────┘ │
│                                     │
│ Extended description (optional)     │
│ ┌─────────────────────────────────┐ │
│ │                                 │ │  ← longer explanation
│ └─────────────────────────────────┘ │
│                                     │
│ ● Commit directly to main branch   │
│ ○ Create a new branch              │
│                                     │
│         [ Commit changes ]          │
└─────────────────────────────────────┘
```

| Field | What it does |
|---|---|
| **Commit message** | The label on that snapshot. Future you reads this when something breaks. Be specific. |
| **Extended description** | Optional longer explanation of *why* you made the change |
| **Commit directly to main** | Saves to the official live version immediately |
| **Create a new branch** | Saves to a draft that doesn't affect the live site until you merge it |

---

### Good vs Bad Commit Messages

```
Good (specific — tells you what changed):
✅ "Add Firebase connection to saveST function"
✅ "Fix final pick [object Object] bug"
✅ "Update scoring from 200 to 225 points"
✅ "Add monthly budget categories"

Bad (too vague — useless in 3 months):
❌ "update"
❌ "fix stuff"
❌ "changes"
❌ "asdfgh"
```

Why does the message matter? When something breaks 3 months from now and you need to find when it broke, good messages let you scan history in seconds.

---

### GitHub Commits vs Google Docs Version History

| Google Docs | GitHub Commit |
|---|---|
| Auto-saves every few seconds silently | You choose exactly when to save |
| Version history exists but is hard to find | Every version is front and center |
| No description of what changed | You write exactly what and why |
| Hard to go back to a specific old version | One click to any past version |
| Only one file | Entire project folder snapshotted |

Google Docs saves *for* you. GitHub makes you save *intentionally* with a description. That intentionality is the whole point — it turns your project history into a readable story.

---

### Practical Rule for Your Projects

Every time Claude helps you add a feature or fix a bug, commit immediately after with a specific message:

```
✅ "Add Firebase real-time sync"
✅ "Fix Round 3 submit button not firing"
✅ "Add zero-sum budget category tracker"
✅ "Fix monthly total calculation"
```

Six months from now when something breaks you'll scan that history, find exactly when it went wrong, and restore any previous version in one click.

---


---

## Firebase — What It Is and How It Works

### The One-Line Explanation
Firebase is Google's hosted backend. Instead of building and running your own server, Google runs it for you. Your frontend app talks directly to Firebase to read and write data.

---

### The Restaurant Analogy
- **GitHub Pages** = The building. Its only job is to hand the customer the menu (your HTML file). It doesn't cook, remember orders, or know who you are.
- **Firebase** = The kitchen + waiter + manager's notebook. It processes requests, carries data back and forth, and remembers everything about every user.

Together they make a complete app:
```
GitHub Pages          Firebase
"Here's the app"  +   "Here's your data"
      =
A fully working shared web application
```

---

### The Two Modes in Your App

**Before Firebase config (localStorage fallback):**
```
App loads → checks if Firebase configured → NO
→ uses localStorage → data stays in your browser only
→ nobody else can see your data
```

**After Firebase config (real backend):**
```
App loads → checks if Firebase configured → YES
→ connects to Firebase → shows loading spinner
→ reads all pools from Google's servers
→ any device in the world can join
```

The check that controls this lives in the code:
```javascript
const IS_FIREBASE_CONFIGURED =
  FIREBASE_CONFIG.apiKey !== "REPLACE_WITH_YOUR_API_KEY";
```
When the placeholder is replaced with a real key → `true` → Firebase mode.
When it's still a placeholder → `false` → localStorage mode.

---

### The Firebase Config — What Each Value Means

When you register a web app in Firebase you get 7-8 values. Think of them as your app's **mailing address + ID card** so it can find and authenticate with your specific Firebase project:

| Value | What it is | Analogy |
|---|---|---|
| `apiKey` | Identifies your app to Google's servers | Password to knock on the door |
| `authDomain` | Web address used for authentication | Building's street address |
| `databaseURL` | Exact address of YOUR database | Your specific mailbox |
| `projectId` | Your project's unique name in Google's system | Apartment number |
| `storageBucket` | Where files are stored (not used in our app) | Storage unit in basement |
| `messagingSenderId` | Used for push notifications (not used in our app) | Intercom code |
| `appId` | Unique fingerprint for this specific app | Your ID card |
| `measurementId` | Google Analytics ID (optional) | Loyalty card number |

**Is it safe to put these in your code?** Yes — they're designed to be in frontend code anyone can see. The actual security comes from Firebase Rules (see below), not from keeping these values secret.

---

### Firebase Realtime Database

This is the specific Firebase product your app uses. It's a NoSQL database that:
- Stores data as JSON (like a giant nested object)
- Syncs changes to all connected clients in real time (~100ms)
- Works directly from frontend JavaScript — no server needed

**Your data structure:**
```
Firebase Database
└── pools/
    ├── testpool1/
    │   ├── name: "Test Pool"
    │   ├── adminPin: "0000"
    │   ├── joinPassword: "test123"
    │   ├── predRound: 1
    │   ├── tournament: "active"
    │   └── users/
    │       └── u_isabel/ { displayName, pin, rounds, history }
    └── workpool2026/
        ├── name: "Work Pool"
        └── ...
```

Every pool is completely separate. Users in one pool can't see data from another pool.

---

### Firebase Rules — Security

Right now your database is in **test mode** which means anyone can read and write anything for 30 days. That's fine for testing but before going live you should tighten the rules.

**Default test mode rules (expires after 30 days):**
```json
{
  "rules": {
    ".read": "now < 1234567890000",
    ".write": "now < 1234567890000"
  }
}
```

**Better rules for production (to add later):**
```json
{
  "rules": {
    "pools": {
      ".read": true,
      ".write": true
    }
  }
}
```

To edit rules: Firebase Console → Realtime Database → Rules tab.

---

### Firebase Free Tier (Spark Plan)

Your project is on the **Spark plan — $0/month**. The limits are generous for a prediction pool:

| Resource | Free limit | Your likely usage |
|---|---|---|
| Simultaneous connections | 100 | ~20-30 players |
| Storage | 1 GB | A few MB at most |
| Data transfer | 10 GB/month | Well under 1 GB |
| Cost | $0 | $0 |

You will not hit these limits with a World Cup pool. The free tier is permanent (not a trial).

---

### How to Set Up Firebase (Step by Step)

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project** → name it → Continue through the steps
3. Left sidebar → **Databases & Storage → Realtime Database → Create Database**
4. Choose **United States (us-central1)** → **Start in test mode** → Enable
5. Left sidebar → **Settings → General** → scroll to **Your apps**
6. Click the **`</>`** web icon → nickname your app → **Register app**
7. Copy the `firebaseConfig` values shown
8. Paste them into your HTML file replacing the placeholders

---

### The Code Change Is Just 8 Lines

Going from localStorage to Firebase is literally replacing one config object:

```javascript
// BEFORE — placeholders (localStorage fallback)
const FIREBASE_CONFIG = {
  apiKey: "REPLACE_WITH_YOUR_API_KEY",
  ...
};

// AFTER — your real Firebase project
const FIREBASE_CONFIG = {
  apiKey: "AIzaSyC-Sc08xoU3esEErRhI6HMhYY4waahgrWg",
  authDomain: "wc2026pool.firebaseapp.com",
  databaseURL: "https://wc2026pool-default-rtdb.firebaseio.com",
  projectId: "wc2026pool",
  storageBucket: "wc2026pool.firebasestorage.app",
  messagingSenderId: "90400610077",
  appId: "1:90400610077:web:b904dca72b654e8d62f3f4",
  measurementId: "G-7MGZGTR094"
};
```

Everything else — all the app logic, scoring, bracket, admin panel — stays identical. The destination of where data is saved changes. Nothing else does.

---

### Transferable to Your Budgeting App

The exact same Firebase setup works for any app:
1. Create a new Firebase project (or reuse this one with a different path)
2. Same 8 config values
3. Same `loadPool/saveST` pattern → just rename to `loadBudget/saveBudget`
4. Data path changes from `/pools/xyz` to `/budgets/isabel`

One Firebase account can host unlimited projects. You already know the setup flow now.


---

*Last updated: May 2026 — World Cup 2026 Pool project · GitHub · Firebase*
