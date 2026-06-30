# PicoCTF: Forensics - Binary digits

## 🎯 Objective
Extract the hidden flag from a raw binary string masquerading as a text file.

## 🛠️ Tools & Concepts Used
* `Binary Data Representation` - Understanding how files (like images) are fundamentally stored as sequences of 1s and 0s.
* `File Signatures / Magic Numbers` - Recognizing standard hex values (like `FF D8 FF E0`) that identify specific file types (like JPEG).
* `Python (File I/O & Byte Manipulation)` - Using scripting to read text, parse it into integers, and write it out as a raw binary file.

## 📝 Step-by-Step Solution

**1. Inspect the Data**
The challenge provided a file (`digits.bin`) containing a massive string of 1s and 0s. Grouping the first few bits into 8-bit bytes and converting them to hex revealed the standard signature for a JPEG image (`FF D8 FF E0... JFIF`).

**2. Write a Recovery Script**
Since the data was a literal string of text representing binary, it needed to be converted back into an actual binary file structure. I used a short Python script to read the text file, convert the 8-character chunks into integers, and write those bytes to a new `.jpg` file.

```python
with open("digits.bin", "r") as file:
    binary_string = file.read().strip() 

byte_list = [int(binary_string[i:i+8], 2) for i in range(0, len(binary_string), 8)]
byte_array = bytearray(byte_list)

with open("recovered_image.jpg", "wb") as image_file:
    image_file.write(byte_array)
```
**3. Open the Recovered Image**
Running the script generated a valid JPEG file. Opening the image revealed the flag written in plain text across the picture.

## 💡 Key Takeaway
Binary data isn't just executable code; any file type (images, audio, etc.) can be represented as a string of 1s and 0s, and scripting is the fastest way to reassemble it.