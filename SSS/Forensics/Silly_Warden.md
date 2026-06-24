# SSS: Forensics - Silly Warden

## 🎯 Objective
Reveal the invisible text hidden on the page to recover the flag.

## 🛠️ Tools & Concepts Used
* `Ctrl + A` / `Cmd + A` - the universal keyboard shortcut for "Select All"
* `Visual Steganography` - hiding information in plain sight using matching foreground and background colors

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** The flag might be hidden in the file's metadata, the source code, or requires complex forensic tools to extract.
* **Action:** I initially thought about overanalyzing the file, inspecting elements, or searching for hidden embedded files.
* **Result:** I overcomplicated the problem. Before diving into advanced forensic analysis, it is always best to check for the most basic tricks first.

## 📝 Step-by-Step Solution

**1. Open the challenge**
First, I opened the provided file/page. It appeared entirely blank, or seemingly empty, as if nothing was there.

**2. Select all text**
I suspected the text was made invisible by matching the font color to the background color (white text on a white background). I simply pressed Ctrl + A on my keyboard to select everything on the screen.

**3. Reveal the flag**
Highlighting the text inverted the colors, creating a contrast that immediately revealed the hidden text containing the flag.


## 💡 Key Takeaway
Sometimes the simplest solution is the correct one. Always check for basic visual tricks—like white-on-white text—before moving on to advanced forensics.