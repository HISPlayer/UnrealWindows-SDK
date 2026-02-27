# Playing Local Files

HISPlayer Windows for Unreal supports playback of local video content using:

- **Absolute file paths** (from your Windows machine)  
- **Project-relative paths** (from your Unreal project's `Content` folder)

---

## Using Absolute Paths (PC Storage)

You can load video files directly from your Windows machine using the full absolute path.

Example: C:/Users/YourUser/Videos/movie.mp4

To configure it:

1. Select **BP_HISPlayer** in the Level Outliner.  
2. Open the **Details** panel.  
3. Locate the **HISPlayer** section.  
4. Enter the full absolute file path into the **Stream URL** field.

<p align="center">
<img width="956" height="675" alt="image" src="https://github.com/user-attachments/assets/ec6fa0c0-4f52-44ba-9d62-9fe9349bff60" />
</p>

---

## Using Project-Relative Paths (Content Folder)

You can also play video files stored inside your Unreal project.

### Step 1 – Create the Movies Folder

Inside your Unreal project:

1. Navigate to the main **Content** folder.  
2. Create a directory named: Movies

---

### Step 2 – Add the Video File

Place your video file inside: Content/Movies/

Example: Content/Movies/movie.mp4

> ⚠ It is important that the actual video file exists inside the `Content/Movies` folder. The `.uasset` file alone is not sufficient.

---

### Step 3 – Set the Relative Path

In the **Stream URL** field of **BP_HISPlayer**, enter the path relative to the `Content` folder.

Example: Movies/movie.mp4

Do not include `Content/` in the path.

<p align="center">
<img width="955" height="674" alt="image" src="https://github.com/user-attachments/assets/2844dcce-b1ba-4304-81b1-cb02fc8a53a2" />
</p>

---

## Notes

- Forward slashes `/` should be used in paths.  
- Ensure the video format is supported (e.g., MP4, AVI).  
- If the video does not play, verify that the file exists physically inside the project directory.
