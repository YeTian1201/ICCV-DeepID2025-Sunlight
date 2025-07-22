# 🆔 DeepID: Digital Manipulation Detection in ID Documents

## 📌 Overview & Motivation

With the rapid advancement of **visual generative models**, digital manipulation of ID documents has become a real-world threat.  
**DeepID** is the **first competition** focused specifically on detecting **injected digital manipulations** (not presentation attacks) in ID cards and passports.

### The core objectives are:

- ✅ **Detect face-swapping** attacks in ID photos  
- ✅ **Detect text inpainting** in fields like name, date of birth, or ID number  
- ✅ **Localize forgeries at the pixel level** (automated visual forensics)  
- ✅ Ensure **practical deployability** under memory and computation constraints  

---

## 🏁 Competition Tracks

### 🔹 Track 1: Binary Classification (Real vs. Forged)

- **Input**: A single ID card image  
- **Output**: A score between `0` and `1`  
  - Closer to `1`: bonafide (real)  
  - Closer to `0`: forged  
- **Evaluation**: F1-score (with a fixed threshold at 0.5)

---

### 🔹 Track 2: Manipulation Localization (Binary Mask Prediction)

- **Input**: A single ID image  
- **Output**: A binary mask with the same dimensions as the input  
  - Value `1`: bona fide (clean)  
  - Value `0`: forged/manipulated region  
- **Evaluation**: Image-level aggregated F1-score  

---

## 📦 Dataset Overview

### 🧾 Fantasy ID Dataset (for training/tuning)

- **262 fantasy ID templates**, designed to mimic real ID documents of 10 countries  
- **786 bona fide images** captured using:
  - iPhone 15 Pro  
  - Huawei Mate 30  
  - Kyocera TASKalfa 2554ci scanner  
- **1,572 manipulated samples** created using:
  - 2 face-swapping techniques  
  - 2 text inpainting techniques  
- Faces are taken from public datasets:
  - AMFD, Face London, HQ-WMCA  
- Dataset will be released in **August 2025** under **CC BY 4.0**

---

## 🧪 Test Sets

### 🔸 In-domain Test Set

- Based on **new Fantasy ID cards**  
- Includes **novel manipulation techniques** not present in training  
- Evaluation leaderboard updated **daily**

### 🔸 Private Out-of-domain Test Set (Hidden)

- Provided by **PXL Vision** using **real ID documents** and corresponding forgeries  
- **Not publicly released**  
- Used for realism & generalization evaluation  
- Leaderboard updated **daily**

---


## 📂 Fantasy ID Dataset Examples



### 🟩 `original`
Original digital Fantasy ID card designs (before printing/scanning).

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="original/chinese-NF-1042.png" height="150px"/> | <img src="original/portugal-066_03.png" height="150px"/> | <img src="original/turkiye-NF-1054.png" height="150px"/> |


---

### 🟦 `bonafide` 

Captured from printed ID cards using different devices.

#### 📱 iPhone 15 Pro

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="bonafide\iphone15pro\chinese-NF-1042.jpg" height="150px"/> | <img src="bonafide\iphone15pro\portugal-066_03.jpg" height="150px"/> | <img src="bonafide\iphone15pro\turkiye-NF-1054.jpg" height="150px"/> |


#### 📱 Huawei Mate 30

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="bonafide\huawei\chinese-NF-1042.jpg" height="150px"/> | <img src="bonafide\huawei\portugal-066_03.jpg" height="150px"/> | <img src="bonafide\huawei\turkiye-NF-1054.jpg" height="150px"/> |

#### 🖨️ Kyocera TASKalfa 2554ci

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="bonafide\scan\chinese-NF-1042.jpg" height="150px"/> | <img src="bonafide\scan\portugal-066_03.jpg" height="150px"/> | <img src="bonafide\scan\turkiye-NF-1054.jpg" height="150px"/> |

---

### 🟥 `attack` (Digital Manipulations)

Manipulations include face-swapping and text inpainting.

---
#### 🔺 Digital Manipulations-1

##### 📱 iPhone 15 Pro

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="attack\Digital Manipulations-1\iphone15pro_red\chinese-NF-1042.jpg" height="150px"/> | <img src="attack\Digital Manipulations-1\iphone15pro_red\portugal-066_03.jpg" height="150px"/> | <img src="attack\Digital Manipulations-1\iphone15pro_red\turkiye-NF-1054.jpg" height="150px"/> |


##### 📱 Huawei Mate 30

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="attack\Digital Manipulations-1\huawei_red\chinese-NF-1042.jpg" height="150px"/> | <img src="attack\Digital Manipulations-1\huawei_red\portugal-066_03.jpg" height="150px"/> | <img src="attack\Digital Manipulations-1\huawei_red\turkiye-NF-1054.jpg" height="150px"/> |


##### 🖨️ Kyocera TASKalfa 2554ci

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="attack\Digital Manipulations-1\scan_red\chinese-NF-1042.jpg" height="150px"/> | <img src="attack\Digital Manipulations-1\scan_red\portugal-066_03.jpg" height="150px"/> | <img src="attack\Digital Manipulations-1\scan_red\turkiye-NF-1054.jpg" height="150px"/> |

---
#### 🔺 Digital Manipulations-2

##### 📱 iPhone 15 Pro

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="attack\Digital Manipulations-2\iphone15pro_red\chinese-NF-1042.jpg" height="150px"/> | <img src="attack\Digital Manipulations-2\iphone15pro_red\portugal-066_03.jpg" height="150px"/> | <img src="attack\Digital Manipulations-2\iphone15pro_red\turkiye-NF-1054.jpg" height="150px"/> |


##### 📱 Huawei Mate 30

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="attack\Digital Manipulations-2\huawei_red\chinese-NF-1042.jpg" height="150px"/> | <img src="attack\Digital Manipulations-2\huawei_red\portugal-066_03.jpg" height="150px"/> | <img src="attack\Digital Manipulations-2\huawei_red\turkiye-NF-1054.jpg" height="150px"/> |


##### 🖨️ Kyocera TASKalfa 2554ci

|Chinese | Portugal | Turkiye |
|----------|----------|----------|
| <img src="attack\Digital Manipulations-2\scan_red\chinese-NF-1042.jpg" height="150px"/> | <img src="attack\Digital Manipulations-2\scan_red\portugal-066_03.jpg" height="150px"/> | <img src="attack\Digital Manipulations-2\scan_red\turkiye-NF-1054.jpg" height="150px"/> |

---




## 📊 Final Scoring (Aggregate F1 Score)

Final ranking uses a **weighted F1 score** formula:

$$
\text{Aggregate\_F1} = 0.3 \times \text{F1}_{\text{fantasy}} + 0.7 \times \text{F1}_{\text{private}}
$$



Where:

- `F1_fantasy` = average of F1 on bona fide and attack samples from the Fantasy test set  
- `F1_private` = F1-score on the private real document test set  
