# SSS: Forensics - Ice Miner

## 🎯 Objective
Repair the corrupted file header and remove the junk data to recover the hidden image and find the flag.

## 🛠️ Tools & Concepts Used
* `VS Code` - text and source code editor used for initial file inspection
* `Hex Editor` - tool used to view and modify the raw binary data of the file
* `Magic Bytes` - file signatures used to identify the format of a file (e.g., the standard PNG header)

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** The file might just be a standard text file or log since it opens in a text editor.
* **Action:** I opened the file in VS Code to read the contents.
* **Result:** While there was text at the beginning, the presence of non-printable characters and a near-match for a PNG header indicated it was actually a corrupted image file.

## 📝 Step-by-Step Solution

**1. Initial Inspection in VS Code**
First, I opened the file in VS Code. I noticed some text at the very beginning, followed by a series of "magic bytes." However, the header was slightly corrupted—it read "POG" instead of the standard "PNG". I also noticed many non-printable characters towards the end of the file.

**2. Open in a Hex Editor**
Realizing the file was a corrupted image, I opened it in a Hex Editor to safely manipulate the raw bytes.

**3. Remove the Junk Text**
Inside the Hex Editor, I deleted the initial paragraph of text entirely, stopping right where the image header began.

**4. Fix the Magic Bytes**
Next, I navigated to the corrupted magic bytes and modified the incorrect `O` to an `N`, effectively restoring the standard `PNG` file signature.

**5. Save and Reveal the Flag**
Finally, I saved the modified file with a .png extension. When I opened the resulting image, it successfully rendered and displayed the flag.

## 💡 Key Takeaway
I learned how to identify file types using magic bytes and how to manually repair a corrupted file header using a Hex Editor.
