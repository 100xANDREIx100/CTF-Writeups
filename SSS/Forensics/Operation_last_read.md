# SSS: Forensics - Operation Last Read

## 🎯 Objective
Find the flag in the pdf file

## 🛠️ Tools & Concepts Used
* `binwalk` - a tool used for searching a file for embedded files and executable code
* `grep` - search for a specific pattern of characters.

## 🕳️ Rabbit Holes & Missteps
* **Hypothesis:** The key is hidden somewhere in the metadata of the file
* **Action:** I tried `strings sssforensics.pdf | grep SSS*`
* **Result:** I got 2 fake flags that pointed that this method is of no value here

* **Hypothesis:** The flag is at plain sight written with white text over a white background
* **Action:** I tried to extract the text using `pdftotext sssforensics.pdf`
* **Result:** THere was nothing hidden there

## 📝 Step-by-Step Solution

**1. Search for Hidden FIles**
First, I searched for any hidden files inside using `binwalk`

```bash
binwalk sssforensics.pdf
```

**2. Extract the flag**
Then, inside the created directory `_sssforensics.pdf.extracted` I found a couple of files out of which a text file whom I simply read with grep
```bash
grep SSS* pdf.txt
```

There I found the flag `SSS{poti_sa_te_ascunzi_dar_nu_te_poti_ascunde}`

## 💡 Key Takeaway
I learned how to use `binwalk`