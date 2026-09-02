# MoVIZ - Data Extraction Workflow

Thank you for your interest in this data extraction workflow. Follow the
instructions below to install and run it locally.

## Requirements

- [KNIME Analytics Platform](https://www.knime.com/downloads/overview) 5.12.0
  or newer
- The workflow file (`.knwf`)
- The MoVIZ - Data Extraction extension installation package downloaded from
  the [extension repository](https://github.com/joseteofilo/knime-python-extension-data-extraction-wf/releases)

The extension package includes the Python dependencies required by its nodes.
No separate Python environment setup is required.

## Install the Extension

1. Download the extension installation package from the extension
   repository. Download the packaged update-site archive, not the repository's
   **Source code** ZIP file.
2. Extract the downloaded archive to a local folder.
3. Locate the extracted folder that contains both `content.jar` and
   `artifacts.jar`. This is the folder that must be registered in KNIME. If
   the files are inside an additional subfolder, use that subfolder instead.
4. Open KNIME Analytics Platform.
5. Open **File > Preferences**.
6. Select **Install/Update > Available Software Sites**.
7. Click **Add...**, enter a name such as `MoVIZ - Data Extraction`, and
   select the extracted folder containing `content.jar` and `artifacts.jar` as
   its location.
8. Click **Apply and Close**.
9. Open **File > Install KNIME Extensions...**.
10. Select the newly added MoVIZ update site and install **MoVIZ - Data
    Extraction**.
11. Accept the license terms and complete the installation.
12. Restart KNIME when prompted.

After restarting, the nodes are available under **Community Nodes > MoVIZ -
Data Extraction**.

## Prerequisites - GROBID

- [GROBID Installation Guide](https://grobid.readthedocs.io/en/latest/Install-Grobid/)
    - **Requires JAVA:**  
      For building GROBID yourself, a JDK must be installed on your machine. We tested the tool successfully from JDK 1.11 up to JDK 1.17. Other recent JDK versions should work correctly.
    - **Source Code Download:**  
      - Download from GitHub: [grobid-0.8.0.zip](https://github.com/kermitt2/grobid/archive/0.8.0.zip)
      - Unzip the folder `grobid-0.8.0`
      - Place it in a folder without any spaces in the name
    - **Building and Running GROBID:**
      1. Navigate to the `grobid-0.8.0` folder:
          - `cd grobid-0.8.0`
      2. Run the build command:
          - `./gradlew clean install`
      3. Start the local server with the command:
          - `./gradlew run`
          - Check the server at: [http://localhost:8070/](http://localhost:8070/)
      4. **Important:** Ensure the local server is started **before** executing the workflow.
    - **Platform Note:**
      - [Windows-related issues](https://grobid.readthedocs.io/en/latest/Frequently-asked-questions/#windows-related-issues):  
        Windows, unfortunately, is currently not supported, due to lack of experience and time constraints.

## Run the Workflow

1. Download the workflow: [Data Extraction Workflow](https://hub.knime.com/s/uA68Gz0jfpcUt_X7).
2. In KNIME Analytics Platform, select your **Local Space**.
3. In your local space, select **Import Workflow**.
4. Browse to the workflow file you downloaded. It will have the `.knwf`
   extension.
5. Open the imported workflow.
6. If you use a GROBID node, start the local GROBID server before executing
   the workflow.
7. Run the workflow with your data.
