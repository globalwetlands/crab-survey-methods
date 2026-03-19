---
title: "Field procedures"
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

The following criteria and procedures ensure consistency in the collection and organization of data across monitoring areas (remember the hierarchy: Country, Location, Site, and Point. The primary sampling unit is a Point, which is a single camera deployment. At least three cameras must be deployed per Site. A Location should have at least two sites, including a refernece and at least one restore or degraded site. Please refer to the GLOW Location and Site selection guidelines document for an explanation of what a reference, restored or degraded sites are.

For the purposes of this chapter, a fieldtrip is an event comprising several camera deployments at one or multiple sites.

## Fieldtrip documentation and metadata

Because of the global scale of our project, every sample collected must be accompanied by a complete metadata record and every fieldtrip must be documented. In a multi-country study as ours, metadata acts as the key context information that allows us to compare data from a mangrove forest in Brazil to one in Vietnam. Without this context, biological data, such as crab activity or population counts, loses its scientific value because we cannot account for environmental or technical variables.

Properly documenting metadata ensures **reproducibility** and **data integrity**. For instance, knowing the exact equipment settings or the specific roles of the team allows future researchers to understand exactly how a result was captured, ensuring that our global monitoring of mangrove crabs remains a robust, long-term dataset.

### Site level metadata: documenting fieldtrips

The following information must be recorded for every fieldtrip to provide the necessary context for analysis:

- **Fieldtrip details:** Explicitly state the country, locations, start/end dates, and primary research aims to ensure the data is geographically and temporally searchable.
- **Participant roles:** List all participants, affiliations, and specific roles (e.g., field lead, data capture, support). This maintains accountability and allows for follow-up on specific data points.
- **Equipment specifications:** Record camera types (e.g., GoPro Hero 12, GuardPor Trail camera), settings, and configurations of any additional sampling equipment (e.g., AudioMoth, PhysChem probe, salinometer). Differences in frame rates or sensor sensitivity can significantly impact crab detection rates and must be accounted in analysis.
- **General array description:** Provide a standardized description of the deployment setup, including the number and type of cameras, camera-stand type, and recording durations per day.

### Sample (Point) level metadata: ensuring data tracebility

While Site level metadata covers the broadly "Who", "Where", "When" and "How" **Sample (Point) level metadata** captures the precise "When" and "How" for every individual camera deployed (i.e. Point). In a global program, we face a significant technical risk: multiple teams using identical camera models will generate identical filenames (e.g., `GOPR0001.MP4`). This challenge also occurs within local teams as often each local team will have several identical camera units. Without strict metadata, these files become impossible to distinguish once they reach our central servers.

To prevent data "collisions" and ensure every crab sighting can be traced back to a specific physical location and hardware unit, all equipment must be physically labeled and cross-referenced in the [Master Data Spreadsheet](link to be added).

Below we suggest mandatory Sample (Point) fields. Every camera deployment must be logged as a unique entry in the master file using these mandatory fields:

- **Identify sample position and time:** Record the exact Date (dd/mm/yyyy e.g. 31/12/2025), Time (hh:mm in 24h format, e.g. 13:31) and GPS coordinates in Decimal Degrees (DD, e.g. -27.80501, 153.42602). Use tools such as GLandNav for GPS coordinate conversions. This ensures the sample is placed correctly in our global GIS layers.
- **Site information:** Identify the Location, Site Name, and Site status (e.g., Reference, Restored, Degraded). This allows us to compare crab activity across different mangrove health gradients.
- **Environmental context:** Note the weather (e.g., Overcast, Mostly Sunny), Temperature (daily low/high), Windspeed (kph), Tide (height and time), Rain (% chance and mm), and Cloud Cover (in oktas). These variables are critical for normalizing crab activity models.
- **Camera height from sediment**: Record the camera height from sediment.
- **Hardware traceability:** Track the specific **Camera Type** and **Unique Camera ID** (e.g., GoPro-01, GoPro-02, TrailCamera-005).
  - **Labeling:** All cameras and SD cards must have physical labels.
  - **Mapping:** A Camera ID must be linked to the specific camera entry in the metadata spreadsheet. This prevents confounding data if cameras are swapped or settings are changed between deployments. Remember that sample, Points and camera deployments are the same and our sampling unit.
  - **SD Management:** Ideally, the same SD card should stay with the same camera throughout a trip to maintain a consistent file-naming sequence.
- **Media directory**: Once data is copied to a permanent storage, include the location and directory/file paths associated to the sample in the storage. This is explained in the next section about data management.

## Camera deployment procedure

The field team will require the following materials and equipment. These should be verified and tested before field trip.

1. Camera rig or mounting unit
2. Trail camera (fully charged, batteries installed, empty SD card)
3. GPS
4. A second handheld camera, e.g. phone camera is sufficient
5. Reference quadrat (50cm x 50cm) with markings every 10 centimetres on each side.
6. Fieldwork datasheet or notebook, and pen / pencil
7. Microfibre cloth for wiping and cleaning cameras

Follow the procedure below for starting sampling:

1. Verify that the camera is fully charged and the SD card is formatted (empty).
2. Locate your sampling location, Point, in one of the two microhabitats. Take a GPS waypoint and record the waypoint number in fieldwork datasheet.
3. Check that the camera lens is clean; wipe down with a microfibre cloth if necessary. If using GoPro cameras inside a case, ensure that the camera lens is clean, but also the internal and external sections of the case's lens port.
4. Place down the camera mounting in the camera rig. Verify the reference quadrat (50cm x 50cm) is visible in the field of view of the camera. This is a key step, and the field team must ensure the reference quadrat is fully visible, all four corners are inside the camera field of view. Start the timelapse recording.. Leave the quadrat to be visible by camera for at least 1 or 2 minutes, depending on timelapse frequency. We want to ensure quadrat is visible in at least few frames. After 1 or 2 minutes remove the reference quadrat ensuring that camera and rig are not moved.
5. While waiting for the 1 or 2 minutes the reference quadrat remains visible by the camera, fill out the fieldwork datasheet. Whether deploying underneath the canopy or in a gap area, take a photo of the canopy directly above the camera monitoring unit. Place the second camera (e.g. phone camera) parallel to horizon and take a snapshoot towards the sky, avoid people is included in the picture.
6. Remember, after 1 or 2 minutes, and after datasheet is completely filled, retrieve the quadrat and exit the site, leaving only the camera monitoring unit. **Avoid moving the camera or camera rig**
7. Repeat the procedure as many times as Points (camera deployments) are completed.
8. Ensure that the fieldwork datasheet is filled with all data before leaving the site.

Important deployment notes:

1. Ensure that the camera settings are set correctly prior to the camera deployment (see section on recommended trail camera settings).
2. Deploy in an area that has signs of crab activity such as burrows, bioturbation, etc.
3. Do not place the monitoring unit above thick vegetation, overgrown areas, or thick roots.
4. Ensure that the monitoring unit is placed on a flat and level surface in one of the two microhabitats (canopy gap and underneath the tree canopy).
5. The camera must NOT be submerged at any point during the high tide.
6. Ensure that the spot you have selected has sufficient lighting for the camera. For trail cameras, you can check this by using the live image. This will appear in black & white if lighting is insufficient - in this case, avoid that spot.
7. Obtain an equal number of deployments (samples) for each of the two microhabitats (canopy gap and underneath the tree canopy).

During camera retrieval ensure that all cameras are accounted and collected back. Take note of any observation associated to the environment where cameras were deployed or the camera and rig combo, such as: camera fallen, branch fallen, camera flooded, extreme weather events, etc. Ensure all equipment is rinse and clean after is collected back.

**Priotise copying and backing up media in cameras as soon as possible**
