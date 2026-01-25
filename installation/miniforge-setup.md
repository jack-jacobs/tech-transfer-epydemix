# Miniforge Setup Guide

## Why Miniforge?

Anaconda is a proprietary product that may require a paid license for certain organizational use under its [Terms of Service](https://www.anaconda.com/legal/terms/terms-of-service). Organizations with more than 200 employees/contractors (including affiliated entities) may need a commercial license unless the use qualifies under Anaconda's free-use categories (e.g., personal non-commercial use, eligible academic use, or eligible non-profit/research use).

**Miniforge** is an equivalent alternative that:
- Does not require an Anaconda commercial license
- Has permissive usage policies
- Is community-driven and non-proprietary

## Differences from Anaconda

| Feature | Anaconda | Miniforge |
|---------|----------|-----------|
| GUI launcher | Yes (Anaconda Navigator) | No (command line only) |
| Package repositories | Anaconda's proprietary repos | conda-forge (community-driven) |
| Commercial license required | Yes, for some organizations | No |
| Package coverage | Comprehensive | Largely equivalent for most use cases |

## Installation

### Step 1: Download Miniforge

Download the installer for your operating system from the official conda-forge page:

👉 **[https://conda-forge.org/download/](https://conda-forge.org/download/)**

Choose the appropriate installer:
- **Windows**: `Miniforge3-Windows-x86_64.exe`
- **macOS (Intel)**: `Miniforge3-MacOSX-x86_64.sh`
- **macOS (Apple Silicon)**: `Miniforge3-MacOSX-arm64.sh`
- **Linux**: `Miniforge3-Linux-x86_64.sh`

### Step 2: Run the Installer

#### Windows
1. Double-click the downloaded `.exe` file
2. Follow the installation wizard
3. Accept the default options (or customize as needed)

#### macOS / Linux
1. Open a terminal
2. Navigate to your Downloads folder:
   ```bash
   cd ~/Downloads
   ```
3. Run the installer:
   ```bash
   bash Miniforge3-<your-platform>.sh
   ```
4. Follow the prompts and accept the license agreement
5. When asked to initialize Miniforge, type `yes`

### Step 3: Verify Installation

Open a **new terminal window** and run:

```bash
conda --version
```

You should see output like `conda 24.x.x` (version number may vary).

## Creating the Workshop Environment

Once Miniforge is installed, create the workshop environment:

```bash
conda create -n epydemix-workshop python=3.11 -y
conda activate epydemix-workshop
```

Install required packages:

```bash
conda install jupyter numpy pandas matplotlib -y
pip install epydemix
```

## Starting Jupyter Notebook

Since Miniforge does not include a GUI launcher, start Jupyter from the command line:

```bash
conda activate epydemix-workshop
jupyter notebook
```

This will open Jupyter Notebook in your default web browser.

## Troubleshooting

### `conda` command not found
- Close and reopen your terminal after installation
- On macOS/Linux, you may need to run: `source ~/.bashrc` or `source ~/.zshrc`

### Permission issues on macOS/Linux
Make the installer executable first:
```bash
chmod +x Miniforge3-<your-platform>.sh
```

## Need Help?

If you run into any issues with setup, please let us know. Technical assistance will be provided on-site during the workshop.
