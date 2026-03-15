# Drug Design CURE Project Using Interactive MD in Virtual Reality

**Course:** General Chemistry II Laboratory (CURE Section)  
**Institution:** CUNY Hostos Community College  
**Instructor:** Anna K. Manukyan, Ph.D. — [amanukyan@hostos.cuny.edu](mailto:amanukyan@hostos.cuny.edu)  
**Associated publication:** Manukyan, A.K. "Interactive Molecular Dynamics in Virtual Reality: A CURE Framework for General Chemistry II." *Journal of College Science Teaching* (in revision).

---

## What Is This Repository?

This repository contains all supplementary instructional materials for a course-based undergraduate research experience (CURE) embedded in a General Chemistry II laboratory course. Students investigate how different inhibitor scaffolds (statine, AHPPA, HEA) affect the conformational flexibility of the HTLV-1 protease polyproline loop using interactive molecular dynamics in virtual reality (iMD-VR) and Python-based trajectory analysis.

All materials are designed for students with **no prior programming or biochemistry background**. Every notebook includes pre-computed fallback data so analysis can be completed even if simulation files are temporarily unavailable.

---

## Repository Structure

```
HTLV1-CURE-Materials/
│
├── README.md                          ← You are here
│
├── student_materials/
│   ├── S1_HTLV1_Protease_Primer.pdf       ← Background reading (Gen Chem II level)
│   ├── S2_Curated_Literature_Packet.pdf   ← 5 articles with guided questions
│   ├── S4_Research_Proposal_Template.docx ← Week 8 proposal template + rubric
│   ├── S5_Assessment_Rubrics.pdf          ← All 6 course rubrics
│   ├── S6_Manuscript_Template.docx        ← ACS-style manuscript template
│   └── S6_Poster_Template.pptx            ← 36×48" poster layout template
│
├── notebooks/
│   ├── Notebook_1_Colab_DataAnalysis.ipynb    ← Weeks 2–3: Python intro
│   ├── Notebook_2_MolecularData_PDB.ipynb     ← Week 4: PDB files
│   ├── Notebook_3_Lysozyme_RMSD.ipynb         ← Weeks 5–6: RMSD dress rehearsal
│   ├── Notebook_4_HydrogenBondAnalysis.ipynb  ← Weeks 6–7: H-bond analysis
│   └── Notebook_5_HTLV1_Pipeline.ipynb        ← Weeks 9–11: Full research pipeline
│
├── trajectories/
│   ├── lysozyme_md.pdb                ← Lysozyme topology (dress rehearsal)
│   ├── lysozyme_md.xtc                ← Lysozyme 10 ns trajectory
│   ├── htlv1_statine_bound.pdb        ← HTLV-1 protease + statine topology
│   ├── htlv1_statine_bound.xtc        ← Statine-bound trajectory (10 ns)
│   ├── htlv1_ahppa_bound.pdb          ← HTLV-1 protease + AHPPA topology
│   ├── htlv1_ahppa_bound.xtc          ← AHPPA-bound trajectory (10 ns)
│   ├── htlv1_hea_bound.pdb            ← HTLV-1 protease + HEA topology
│   ├── htlv1_hea_bound.xtc            ← HEA-bound trajectory (10 ns)
│   └── htlv1_apo.xtc                  ← Apo (unbound) protease trajectory
│
├── instructor_materials/
│   ├── S7_Instructor_Implementation_Guide.pdf  ← Week-by-week guide
│   ├── VR_Setup_Instructions.pdf               ← Narupa installation guide
│   └── Sample_Student_Work/
│       ├── exemplary_proposal_annotated.pdf
│       ├── satisfactory_proposal_annotated.pdf
│       └── exemplary_manuscript_excerpt.pdf
│
└── assessment/
    └── S3_Assessment_Plan.pdf              ← IRB-ready assessment protocol
```

> **Note:** Trajectory files are stored using [Git Large File Storage (Git LFS)](https://git-lfs.github.com/) because they exceed GitHub's standard 100 MB file limit. See the **Installation** section for setup instructions.

---

## Quick Start for Students

### Option A — Run in Google Colab (recommended, no installation needed)

Click any badge below to open the notebook directly in Google Colab:

| Notebook | Open in Colab |
|---|---|
| Notebook 1: Python & Data Analysis | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/HTLV1-CURE-Materials/blob/main/notebooks/Notebook_1_Colab_DataAnalysis.ipynb) |
| Notebook 2: Molecular Data & PDB | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/HTLV1-CURE-Materials/blob/main/notebooks/Notebook_2_MolecularData_PDB.ipynb) |
| Notebook 3: Lysozyme RMSD | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/HTLV1-CURE-Materials/blob/main/notebooks/Notebook_3_Lysozyme_RMSD.ipynb) |
| Notebook 4: Hydrogen Bond Analysis | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/HTLV1-CURE-Materials/blob/main/notebooks/Notebook_4_HydrogenBondAnalysis.ipynb) |
| Notebook 5: HTLV-1 Pipeline | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/HTLV1-CURE-Materials/blob/main/notebooks/Notebook_5_HTLV1_Pipeline.ipynb) |

> **Replace `YOUR_USERNAME`** with your GitHub username after uploading files (see instructor setup guide below).

### Option B — Run locally (advanced)

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/HTLV1-CURE-Materials.git
cd HTLV1-CURE-Materials

# 2. Create a virtual environment
python -m venv cure_env
source cure_env/bin/activate      # Mac/Linux
cure_env\Scripts\activate         # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter notebook
```

---

## Installation Guide for Instructors

### Step 1 — Create a GitHub account

If you do not have a GitHub account:
1. Go to [https://github.com](https://github.com)
2. Click **Sign up** and follow the prompts
3. Choose the free plan — it includes everything you need

### Step 2 — Create a new repository

1. Log in to GitHub
2. Click the **+** icon in the top right corner → **New repository**
3. Repository name: `HTLV1-CURE-Materials` (or your preferred name)
4. Set visibility to **Public** (so students can access without logging in)
5. Check **Add a README file**
6. Click **Create repository**

### Step 3 — Install Git on your computer

**Mac:** Git is usually pre-installed. Open Terminal and type `git --version`. If not installed, you will be prompted to install developer tools.

**Windows:** Download Git from [https://git-scm.com/download/win](https://git-scm.com/download/win) and run the installer with default settings.

**Linux:** `sudo apt-get install git` (Ubuntu/Debian) or `sudo yum install git` (CentOS/RHEL)

### Step 4 — Set up Git LFS for large trajectory files

Trajectory files (.xtc) are typically 50–200 MB each and exceed GitHub's standard file limit. Git LFS (Large File Storage) handles these automatically.

```bash
# Install Git LFS
# Mac (using Homebrew):
brew install git-lfs

# Windows: Download from https://git-lfs.github.com and run installer

# Linux:
sudo apt-get install git-lfs

# Initialize LFS in your repository
git lfs install

# Tell Git LFS to track trajectory files
git lfs track "*.xtc"
git lfs track "*.dcd"
git lfs track "*.trr"

# This creates a .gitattributes file — add it to your commit
git add .gitattributes
```

> **GitHub LFS storage:** Free accounts include 1 GB of LFS storage. Trajectory files for this course total approximately 600 MB. This fits within the free tier. If you run multiple semesters and accumulate files, you can purchase additional LFS storage ($5/month for 50 GB).

### Step 5 — Clone your repository and add files

```bash
# Clone your new empty repository to your computer
git clone https://github.com/YOUR_USERNAME/HTLV1-CURE-Materials.git
cd HTLV1-CURE-Materials

# Create the folder structure
mkdir -p student_materials notebooks trajectories instructor_materials assessment
```

### Step 6 — Copy files into the repository folder

Copy all files from this supplementary package into the appropriate folders:

```
student_materials/  ← S1 through S6 documents
notebooks/          ← All 5 .ipynb notebook files
trajectories/       ← PDB and XTC files (when available)
instructor_materials/ ← S7 guide and VR setup instructions
assessment/         ← S3 assessment plan
```

### Step 7 — Commit and push files to GitHub

```bash
# Stage all files for commit
git add .

# Create your first commit
git commit -m "Initial upload: all CURE supplementary materials"

# Push to GitHub
git push origin main
```

You will be prompted for your GitHub username and password (or personal access token — see GitHub's documentation on [creating a personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) if password login fails).

### Step 8 — Verify the upload

1. Go to `https://github.com/YOUR_USERNAME/HTLV1-CURE-Materials` in your browser
2. Confirm that all folders and files appear
3. Click on any notebook file — GitHub will render a preview
4. Click on a trajectory file — it should show "Stored with Git LFS" if LFS is working correctly

### Step 9 — Update the Colab badge links

Open `README.md` in your repository (click the pencil icon to edit online) and replace all instances of `YOUR_USERNAME` with your actual GitHub username. Then click **Commit changes**.

Students can now open any notebook directly in Google Colab by clicking the badge links — no downloads required.

---

## Updating Files During the Semester

When you revise a notebook or document:

```bash
# Navigate to your repository folder
cd HTLV1-CURE-Materials

# Copy the updated file over the old one (same file name)
# Then:
git add notebooks/Notebook_5_HTLV1_Pipeline.ipynb   # or whatever changed
git commit -m "Update Notebook 5: clarify Section 1.2 instructions"
git push origin main
```

Students who open the Colab link will automatically get the latest version.

---

## Adding Trajectory Files as They Become Available

Trajectory files are generated as you set up simulations. Add them progressively:

```bash
cd HTLV1-CURE-Materials/trajectories

# Copy your trajectory files here, then:
git add lysozyme_md.pdb lysozyme_md.xtc
git commit -m "Add lysozyme trajectory for Notebook 3 dress rehearsal"
git push origin main

# Later, add HTLV-1 trajectories:
git add htlv1_statine_bound.pdb htlv1_statine_bound.xtc
git commit -m "Add statine-bound HTLV-1 protease trajectory"
git push origin main
```

---

## Software Requirements

### For students (Notebooks 1–5)
- Google account (for Google Colab — free, no installation)
- Web browser with internet connection

### For instructors (VR simulations)
- **Narupa iMD-VR**: Free, open-source. Download at [https://narupa.readthedocs.io](https://narupa.readthedocs.io)
- **Python 3.8+**: [https://www.python.org/downloads/](https://www.python.org/downloads/)
- **MDAnalysis**: `pip install MDAnalysis`
- **GROMACS** (for running new simulations): Free, download at [https://www.gromacs.org](https://www.gromacs.org)
- VR headset: Meta Quest 2 or 3 (recommended), HTC Vive, or Valve Index

### Python packages (auto-installed by notebooks)
```
numpy >= 1.21
pandas >= 1.3
matplotlib >= 3.4
MDAnalysis >= 2.0
requests >= 2.26
jupyter >= 1.0
```

A `requirements.txt` file is included in the repository for local installation.

---

## Citation

If you use these materials in your own course, please cite:

> Manukyan, A. K. Interactive Molecular Dynamics in Virtual Reality: A CURE Framework for General Chemistry II at a Minority-Serving Institution. *J. Coll. Sci. Teach.* **2026**, in press.

For the Narupa iMD-VR platform:

> Jamieson-Binnie, A. D.; O'Connor, M. B.; Barnoud, J.; Wonnacott, M. D.; Bennie, S. J.; Glowacki, D. R. Narupa iMD: A Scalable Multi-person Interactive Molecular Dynamics Framework for Consensus Assay and Training. *bioRxiv* **2020**, https://doi.org/10.1101/2020.07.09.196220.

---

## License

All instructional materials in this repository are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt these materials for any purpose, provided you give appropriate credit.

Python code in the Jupyter notebooks is additionally licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

## Contact and Support

**Dr. Anna K. Manukyan**  
Department of Natural Sciences  
CUNY Hostos Community College  
475 Grand Concourse, Bronx, NY 10451  
[amanukyan@hostos.cuny.edu](mailto:amanukyan@hostos.cuny.edu)

For questions about adoption, adaptation, or to share your implementation experience, please open a [GitHub Issue](https://github.com/YOUR_USERNAME/HTLV1-CURE-Materials/issues) or send an email. Instructor consultation via video meeting is available upon request.
