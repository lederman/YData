# Setting up Python for YData (S&DS 1230) — Fall 2026

You have two supported ways to work in this course:

| | |
|---|---|
| **A. Your own laptop** | Install Anaconda and import the course environment. Works on Mac and Windows. No command line needed. |
| **B. The Yale cluster** | Use the course's Jupyter portal in your browser. Nothing to install. |

Both are supported. Use whichever you prefer; you can switch at any time.

---

## A. Installing on your own laptop

### A1. Install Anaconda

Download and install the **Anaconda Python distribution** for your operating
system: <https://www.anaconda.com/download>

The full install takes a few minutes and is fairly large. Accept the defaults.

- **Windows** — when it finishes you will also have **Anaconda Prompt**. You
  will not need it unless you want the command-line route below.
- **macOS** — if you are unsure whether your Mac is Apple Silicon or Intel,
  click the Apple menu → About This Mac. "Apple M…" means Apple Silicon. The
  installer page will usually pick the right one for you.

### A2. Download the course environment file

Download **`ydata_fa26.yml`** from this folder or from Canvas. It lists the
packages and versions the course uses. Remember where it saved — usually your
Downloads folder.

### A3. Import the environment

1. Open **Anaconda Navigator** (installed in the previous step).
2. Choose the **Environments** tab on the left.
3. Click **Import** at the bottom.
4. For "Local drive", click the folder icon and choose the `ydata_fa26.yml`
   file you downloaded.
5. Leave the name as **`ydata_fa26`** and click **Import**.

This takes 5–15 minutes and downloads roughly 1 GB. It is normal for it to sit
on "Solving environment" for a minute or two.

> **Do not update packages**, even when Anaconda offers to. Changing versions
> partway through the semester can make exercises stop working. Everyone in the
> course is deliberately on the same versions.

### A4. Start Jupyter

1. In Navigator, go back to the **Home** tab.
2. At the top there is a dropdown that says "Applications on". **Make sure it
   says `ydata_fa26`**, not `base`. This is the step people forget.
3. Click **Launch** under **Jupyter Notebook** (or JupyterLab).

Your browser opens and you can open course notebooks.

**Every time you work on this course, check that dropdown says `ydata_fa26`
before launching.** If it says `base`, Python will not find the course
packages and you will get `ModuleNotFoundError`.

### A5. Check it worked

Open `class_-1.ipynb` from the course materials and run all the cells. If it
runs to the end without errors, you are set up correctly.

### Command line — OPTIONAL, not required

> **You do not need this section.** Steps A1–A5 above are the supported route
> and are enough for everything in the course. This is here only for students
> who already prefer working in a terminal. If you have no idea what a terminal
> is, that is completely fine — skip to the next section and ignore it for the
> rest of the semester. You will not be at any disadvantage.

If you do prefer a terminal, the same setup is:

```bash
conda env create -f ydata_fa26.yml
conda activate ydata_fa26
jupyter lab
```

on macOS in **Terminal**, or on Windows in **Anaconda Prompt** (not the normal
Command Prompt). Remember `conda activate ydata_fa26` in each new window.

---

## B. Using the Yale cluster

The course portal is:

**<https://ydata1230f.ycrc.yale.edu/pun/sys/dashboard/>**

### You must be on the Yale VPN

**The portal is not reachable from the open internet.** You need the Yale VPN
running *before* you open that link — including from a dorm room, a café, or
anywhere off campus. If the page does not load, the VPN is the first thing to
check; a connection error there almost always means the VPN is off, not that
the cluster is down.

Yale's VPN is Cisco Secure Client, from the ITS software page:
<https://software.yale.edu>. Connect to `access.yale.edu`. ITS has setup
instructions for Mac and Windows.

You will also need your **NetID** and **DUO** two-factor authentication to log
in to the portal itself.

### Once you are in

1. Open the **Jupyter** app from the dashboard.
2. In the environment dropdown, choose **`ydata_fa26`**.
3. Click **Launch**, wait for the session to start, then **Connect to Jupyter**.

Two things worth knowing:

- **Closing the browser tab does not end your session.** You must click
  **Delete** on the session when you are done, or it keeps running and uses up
  your allocation.
- You may have at most **4 interactive sessions** at once.

### If the portal will not load

1. Is the VPN connected? (most common cause)
2. Try the address again in full:
   <https://ydata1230f.ycrc.yale.edu/pun/sys/dashboard/>
3. Still stuck — post on Ed with what you see. Do not spend an evening on it;
   your laptop install (Option A) is a fully supported alternative.

---

## Submitting your homework as a PDF

Homework is submitted to Gradescope as a **PDF**. Make one like this:

1. In Jupyter, **File → Save and Export Notebook As… → HTML**
2. Open the downloaded `.html` file in your browser.
3. **File → Print → Destination: Save as PDF**.

That is the whole process. It needs nothing installed beyond what you already
have, and works the same on Mac, Windows, and the cluster.

> Before exporting, run **Kernel → Restart Kernel and Run All Cells** so the
> PDF shows current output for every question rather than a mix of old and new.

### Before you submit — check your PDF

- Every page you expect is present, and nothing is cut off at the right margin.
- Long outputs and wide tables have not run off the page.
- **Mark the pages for each question in Gradescope.** You lose points if the
  grader cannot find your answer.

---

## Troubleshooting

**`ModuleNotFoundError: No module named 'pandas'` (or `YData`, or similar)**
You are almost certainly running in the wrong environment. In Navigator, check
the "Applications on" dropdown says `ydata_fa26`. In Jupyter, check the kernel
name in the top right.

**The Import button in Navigator fails, or solving takes forever**
Make sure you are importing `ydata_fa26.yml` and not an older file. If it still
fails, send us the full error text — the last 20 lines are the useful part.

**`conda: command not found`**
Close and reopen your terminal. On Windows, use **Anaconda Prompt** rather than
the normal Command Prompt. (Or just use Navigator, which needs no terminal.)

**Anything else**
Post on Ed with the exact command you ran and the complete error message.
Screenshots of a terminal are hard to read; copy and paste the text instead.
