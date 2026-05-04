# Participant Setup Instructions

Welcome! This guide will walk you through everything you need to get your computer ready
to start working with the code and demonstrations previewed by ISWS  during the 2026 Chicago Water Week Participatory Groundwater Modeling Event **No prior programming experience
is required** — just follow the steps in order and you will be up and running.

If you get stuck at any point, please reach out to the event organizers
so we can troubleshoot together. Other people might be experiencing the same issue.

---

## What You Will Install

| Tool | Purpose |
|---|---|
| **Git** | Downloads the workshop files to your computer |
| **Miniforge** | Installs Python and the `mamba` package manager |
| **`state-mf6` environment** | A self-contained Python environment with all required packages |
| **Jupyter Notebook** | The browser-based interface used to run the workshop notebooks |

Estimated disk space required: **~4 GB**

---

## Step 1 — Install Git

Git is a tool that lets you download (clone) project code from the internet.

### Windows

1. Go to **[https://git-scm.com/download/win](https://git-scm.com/download/win)**
2. The download will start automatically. Run the installer.
3. Accept all of the default settings — you do **not** need to change anything.
4. When the installer finishes, open the **Start Menu**, search for **"Git Bash"**, and open it.
   You will use this terminal window in later steps.

### macOS

1. Open the **Terminal** app (search for it in Spotlight with `Cmd + Space`, then type `Terminal`).
2. Type the following command and press **Enter**:
   ```
   git --version
   ```
3. If Git is already installed, you will see a version number and can skip to Step 2.
4. If not, macOS will prompt you to install the **Xcode Command Line Tools** — click **Install**
   and follow the prompts. This will install Git automatically.

### Linux

Git is usually already installed. Open a terminal and run:
```bash
git --version
```
If it is not found, install it with your distribution's package manager:
```bash
# Ubuntu / Debian
sudo apt install git

# Fedora / RHEL
sudo dnf install git
```

---

## Step 2 — Install Miniforge (Python + Mamba)

**Miniforge** is a minimal Python installer that includes the `mamba` package manager.
`mamba` is faster than the default `conda` tool and handles the complex package dependencies
in this project very well.

> **If you already have Anaconda or Miniconda installed**, you can skip this step — just
> make sure `conda` is available in your terminal. However, we recommend using `mamba`
> by running `conda install -n base -c conda-forge mamba` after activating your base
> environment.

### Windows

1. Go to **[https://github.com/conda-forge/miniforge/releases/latest](https://github.com/conda-forge/miniforge/releases/latest)**
2. Under **Assets**, download the file named **`Miniforge3-Windows-x86_64.exe`**.
3. Run the installer. When asked about "Add Miniforge3 to my PATH environment variable",
   you can leave it **unchecked** — the installer adds a dedicated **Miniforge Prompt** to
   your Start Menu that you will use instead of Git Bash for the remaining steps.
4. After installation, open the **Start Menu**, search for **"Miniforge Prompt"**, and open it.

### macOS

1. Go to **[https://github.com/conda-forge/miniforge/releases/latest](https://github.com/conda-forge/miniforge/releases/latest)**
2. Under **Assets**, download:
   - **`Miniforge3-MacOSX-arm64.sh`** — if you have a newer Mac with an Apple M1/M2/M3 chip
   - **`Miniforge3-MacOSX-x86_64.sh`** — if you have an older Intel Mac
   
   *(Not sure which chip you have? Click the Apple menu → About This Mac.)*

3. Open the **Terminal** app and navigate to your Downloads folder:
   ```bash
   cd ~/Downloads
   ```
4. Run the installer script (replace the filename if yours is different):
   ```bash
   bash Miniforge3-MacOSX-arm64.sh
   ```
5. Press **Enter** to scroll through the license, then type `yes` to accept it.
6. Accept the default install location by pressing **Enter**.
7. When asked "Do you wish the installer to initialize Miniforge3?", type `yes` and press **Enter**.
8. **Close and reopen the Terminal** for the changes to take effect.

### Linux

1. Go to **[https://github.com/conda-forge/miniforge/releases/latest](https://github.com/conda-forge/miniforge/releases/latest)**
2. Download `Miniforge3-Linux-x86_64.sh` (or the `aarch64` version for ARM systems).
3. In your terminal:
   ```bash
   bash ~/Downloads/Miniforge3-Linux-x86_64.sh
   ```
4. Follow the same prompts as the macOS instructions above.
5. **Close and reopen the terminal** when finished.

### Verify Installation

In your terminal (or Miniforge Prompt on Windows), run:
```bash
mamba --version
```
You should see a version number printed (e.g., `mamba 1.x.x`). If you see an error, try
restarting your terminal first.

---

## Step 3 — Download the Workshop Repository with Git

Now we will use Git to download all of the workshop files to your computer.

1. Open your terminal:
   - **Windows**: Open the **Miniforge Prompt** from the Start Menu
   - **macOS / Linux**: Open the **Terminal** app

2. Navigate to a folder where you want to store the workshop files. For example, your Desktop:
   ```bash
   cd ~/Desktop
   ```
   *(On Windows with the Miniforge Prompt, your home directory is typically `C:\Users\YourName`,
   so `cd Desktop` will work if you are already there.)*

3. Clone the repository:
   ```bash
   git clone https://github.com/iordach1/ISWS-Chi-Water-Week_2026.git
   ```
4. Move into the newly created folder:
   ```bash
   cd ISWS-Chi-Water-Week_2026
   ```

You should now see a folder called `ISWS-Chi-Water-Week_2026` in your chosen location
containing all the workshop files.

---

## Step 4 — Create the Python Environment

This step installs all the Python packages needed for the workshop into an isolated
environment called `state-mf6`. This keeps everything organized and avoids conflicts
with any other Python software on your computer.

> **This step may take 10–20 minutes** depending on your internet speed.

In your terminal, make sure you are inside the `ISWS-Chi-Water-Week_2026` folder
(from Step 3), then run:

```bash
mamba env create -f config/environment.yml
```

You will see a lot of text as packages are downloaded and installed. When it finishes you
should see a message like:

```
done
#
# To activate this environment, use
#
#     $ mamba activate state-mf6
```

---

## Step 5 — Activate the Environment

Every time you start a new terminal session and want to run the workshop notebooks, you
must first **activate** the `state-mf6` environment. This tells Python to use the packages
we just installed.

```bash
mamba activate state-mf6
```

Your terminal prompt will change to show `(state-mf6)` at the beginning, confirming the
environment is active.

---

## Step 6 — Launch the Introductory Notebook in Your Browser

With the environment active, start the Jupyter Notebook server and open the first notebook:

```bash
jupyter notebook python_notebooks/intro_base_model.ipynb
```

This command will:
1. Start a local Jupyter server on your computer
2. Automatically open your default web browser (or print a URL you can copy into your browser)
3. Open the `intro_base_model.ipynb` notebook directly

> **Note:** The Jupyter server runs *in your terminal* — do **not** close that terminal
> window while you are working in the notebook. The browser is just a display interface;
> the actual computation happens in the terminal behind the scenes.

If your browser does not open automatically, look for a line in the terminal output like:
```
http://localhost:8888/tree?token=abc123...
```
Copy that URL and paste it into your browser.

---

## Troubleshooting

### "mamba: command not found" after installation

Close your terminal completely and open a fresh one. If the problem persists, make sure
you answered `yes` when the installer asked about initializing Miniforge.

### Environment creation fails with a package conflict

Try updating mamba first, then re-running the environment creation:
```bash
mamba update -n base mamba
mamba env create -f config/environment.yml
```

### Jupyter opens but the notebook shows a kernel error

Make sure you activated the environment (`conda activate state-mf6`) **before** running
`jupyter notebook`. If the environment is active and the error persists, run:
```bash
python -m ipykernel install --user --name state-mf6 --display-name "Python (state-mf6)"
```
Then refresh the notebook in your browser and select the `Python (state-mf6)` kernel from
the **Kernel → Change kernel** menu.

### MODFLOW simulation does not run (executable not found)

The MODFLOW 6 binary in the `bin/` folder must be executable. On macOS or Linux, fix this with:
```bash
chmod +x bin/mf6
```
On Windows, the `.exe` file should work as-is. If you see a security warning, right-click
the file → Properties → check **Unblock** → OK.

---

## Summary of Terminal Commands

Here is a quick-reference cheat sheet for the commands used in this guide:

```bash
# Navigate to a folder
cd ~/Desktop

# Clone the repository
git clone https://github.com/iordach1/ISWS-Chi-Water-Week_2026.git

# Move into the cloned folder
cd ISWS-Chi-Water-Week_2026

# Create the Python environment (only needed once)
mamba env create -f config/environment.yml

# Activate the environment (needed every new terminal session)
conda activate state-mf6

# Launch Jupyter and open the introductory notebook
jupyter notebook python_notebooks/intro_base_model.ipynb
```

---

*Thank you for exploring groundwater with us! — Vlad Iordache & Daniel Abrams, ISWS*
