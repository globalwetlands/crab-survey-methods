---
title: "Data management"
date: 2026-03-10
authors:
  - name: Nelson Miranda
    affiliation:
      - id: glow-sa
  - name: Diego Gloria
    affiliation:
      - id: glow
  - name: César Herrera
    affiliation:
      - id: glow
---

Managing high-resolution media at a global scale requires a safety-first mindset. The following workflow ensures that every byte of data collected in the field makes it safely to our primary storage and remains searchable for years to come.

## The Transfer-Verify-Backup Protocol

To prevent accidental data loss, never delete original files from an SD card until the following steps are completed:

1. **Direct Copy:** Copy all raw media (images and videos) from the SD card to your primary local storage.
2. **The Redundant Backup:** Create a second copy (a backup) on a separate physical drive or cloud-synced folder.
3. **Integrity Check:** Confirm the file count and total folder size match between the SD card and the two new copies.
4. **Card Clearance:** Only once the backup is verified should you format the SD card for its next deployment.

## Structural Strategy vs. File Renaming

While it is tempting to rename thousands of individual video files to make them clearer, we strongly advise against this.

> **⚠️ Critical Warning:** File renaming is a non-reversible operation. Mass-renaming scripts can easily go wrong, breaking the link between our master metadata spreadsheet and the original file metadata (like internal timestamps).

Instead of renaming files, **rely on a clear Directory and Sub-directory strategy.** By placing raw files into a perfectly structured folder, the folder path itself provides all the context needed without altering the original file name.

### Folder structure & metadata accessibility

To ensure that any researcher (or AI pipeline) can understand the data instantly, your metadata must be **visible and adjacent** to the raw assets.

#### Recommended folder hierarchy:

The following folder hierarchy can be used for any digital storege, such as Hard Drives, Google Drive, and Solid State Drives.

- **Primary (1st) root level** (e.g., `glow-sa-2026-hdd01`, which stand for project `GLOW`, team/country `South Africa`, year `2026` and additional key codes, e.g. referencing one of multiple local storage `hdd01` for Hard Drive 1. Please note that different operating systems impose a maximum length to file paths (usually 256 characters), so avoid using large directory names:
  - This folder acts as the "Home" for all media.
  - **Must contain:** The **Master metadata spreadsheet** with both Site- and Sample-level metadata, and any **Additional Data Spreadsheets** (PhysChem, etc.). Having these files at the root level ensures the map to the data is the first thing anyone sees.
- **Secondary (2nd) level (Date):**
- **Tertiary (3rd) level (Location):** Folders categorized by Location name (e.g., `/Bayhead`, `/Mlalazi`).
- **Quaternary (4th) level (Site):** Folders categorized by Site name (e.g. `/Tingalpa Creek` or `/Bayhead-site01`)
- **Quinary (5th) level (Data Type):** Sub-folders organized by media/instrument type (e.g., `/GoPro_Footage`, `/Camera_Media`, `/Audio_Recordings`, `/Site_Photos`).
- **Sinary (6th) level (Sample/Point):** Unique folders identified by a unique ID representing a camera/instrument and location. We suggest this folder to be named based on camera label, for instance `/trail-cam002` or `/gopro12-004`.
  - **Inside this folder:** Place the raw files and a copy (or shortcut) to the relevant metadata log.

```txt
glow-sa-2026-hdd01/
├── Master_Metadata_GLOW_SA_2026.xlsx
├── PhysChem_Log_SA_2026.csv
├── 2026-01-20/
│   ├── Bayhead/
│   │   ├── Bayhead-site01/
│   │   │   └── Camera_Media/
│   │   │       ├── gopro12-001/
│   │   │       │   ├── GH010001.MP4
│   │   │       │   ├── GH010002.MP4
│   │   │       │   └── metadata_snippet.txt
│   │   │       └── gopro12-002/
│   │   │           ├── GH015432.MP4
│   │   │           └── GH015433.MP4
│   │   │           └── metadata_snippet.txt
│   │   └── Bayhead-site02/
│   │       └── Camera_Media/
│   │           └── gopro12-003/
│   │               ├── GH019988.MP4
│   │               └── GH019989.MP4
│   │               └── metadata_snippet.txt
├── 2026-01-21/
│   └── Mlalazi/
│       ├── Mlalazi-site01/
│       │   └── Camera_Media/
│       │       └── gopro12-004/
│       │           ├── GH011122.MP4
│       │           └── GH011123.MP4
│       │           └── metadata_snippet.txt
│       └── Mlalazi-site02/
│           └── Camera_Media/
│               └── gopro12-005/
│                   ├── GH012233.MP4
│                   └── GH012234.MP4
│                   └── metadata_snippet.txt
```

Always ensure that the **Master metadata spreadsheet** contains direct links or exact path references to these folders. This "searchable index" allows us to jump from a spreadsheet row directly to the specific video of a crab in a specific mangrove site.

#### Key considerations

**Path length management:** By using concise names like `glow-sa-2026-hdd01` and `gopro12-001`, you minimize the risk of hitting the 260-character path limit common in many operating systems (especially Windows), which often causes errors during cloud syncing or deep-learning training.

**Chronological sorting:** Placing the Date at the secondary level allows for easy chronological browsing, which is helpful when comparing crab activity across specific weather events recorded in the metadata. When working with high-definition media, local storage (External Hard Drives/SSDs) will inevitably reach capacity. To manage this without disrupting the organizational logic, we use a Volume-Sequential approach. Name your primary root directories with a suffix indicating the specific hardware unit (e.g., `glow-sa-2026-hdd01`). When `-hdd01` is full, simply initialize `-hdd02` and continue the chronological folder structure (2026-01-22/, etc.) on the new drive. Because the Master Metadata Spreadsheet at the root of each drive acts as the map for that specific volume, you can add new data to a second storage unit without ever needing to move, rename, or risk corrupting the files already finalized on the first drive. Once all drives return from the field, their metadata spreadsheets are merged into a single "Global Master Index," allowing us to locate any specific video across multiple physical hard drives instantly. This ensures that the "Chronological level" (level 2) remains the primary way we navigate time, while the "Root level" (level 1) manages the physical hardware constraints.

**Contextual Isolation:** The Sinary (6th) level ensures that with two or more cameras were recording at the same site, their files never mix. This is our primary defense against filename collisions.

**Metadata Proximity:** The metadata_snippet.txt (or a shortcut to the Master sheet) inside the camera folder ensures that if a single folder is shared with a collaborator, the context travels with the pixels.

## Data QA/QC: Ensuring excellence through collaboration

Quality Assurance (QA) and Quality Control (QC) are not just about catching errors, they are about protecting the hard work you do in the field. This checklist is the final gatekeeper that ensures your data is "Ready" and scientifically robust before it enters our global database.

> **💡 Empowering the Team:** While this list provides our core requirements, it is not a rigid "one-size-fits-all" document. Every mangrove site and team has its own personality. We encourage all teams to **modify, expand, and refine** these points based on your local environmental conditions and logistical realities. If you find a better way to track hardware or a common error we have missed, please update your local version and share those insights with the global community!

### The Pre-Upload checklist

#### 1. Metadata Synchronization

- [ ] **Temporal match:** Does the `Date/Time` on the Master spreadsheet match the `Date Created` metadata on the media files?
- [ ] **Spatial accuracy:** Have GPS coordinates been double-checked against a map to ensure no "typos" have placed a camera in the middle of the ocean?
- [ ] **The "Missing Link":** Is every single Row in the spreadsheet successfully linked to a corresponding Folder or File?

#### 2. Media Integrity & Labeling

- [ ] **Collision check:** Have all files been checked for naming overlaps? (e.g., ensuring two different "GoPro-01" units from different days were not accidentaly place in same folder or overwrite each other).
- [ ] **Visibility check:** Open a random sample (5%) of the videos. Is the lens clear? Is the crab activity visible, or is the framing obscured by vegetation?
- [ ] **Hardware tagging:** Is the `Camera ID` in the spreadsheet correctly reported in the data directory hierarchy?

#### 3. Environmental Logic

- [ ] **Tide consistency:** Do the recorded tide heights align with the visual evidence in the footage (e.g., if the log says "low tide at 14:30", does the camera experienced the lowest visible tide at that time?
- [ ] **Weather context:** Are extreme events (heavy rain, high winds) noted? These are critical for the AI to distinguish between "moving crabs" and "moving shadows/leaves."

#### 4. Your Modifications

- [ ] **Local Variable [Add Yours]:** Explain here
- [ ] **Local Variable [Add Yours]:** Explain here

---

### How to Propose a Protocol Update

If you’ve modified this checklist to solve a local problem:

1. **Highlight the change** in your team’s shared directory.
2. **Add a brief note** explaining why (e.g., _"Added a check for lens salt-spray in high-wind sites"_).
3. **Notify the Global Data Manager** so we can evaluate if this should be adopted by other teams in similar climates.
