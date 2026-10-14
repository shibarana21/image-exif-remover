# EXIF / Metadata Remover Web App - Implementation Plan

## 1. Project Overview
- **Name:** EXIF Remover Web App
- **Goal:** यूजर द्वारा अपलोड की गई इमेज (JPEG, PNG, WebP) से सारा EXIF व निजी मेटाडेटा (GPS, कैमरा मॉडल, तारीख आदि) ब्राउज़र के अंदर ही रिमूव करना।
- **Architecture:** 100% Client-Side (No backend needed), Single-File HTML/CSS/JS या मॉड्युलर स्ट्रक्चर।

## 2. Technical Approach (सबसे आसान व सुरक्षित तरीका)
- **HTML5 Canvas Re-draw:**  1. यूजर इमेज फाइल सेलेक्ट या ड्रैग-एंड-ड्रॉप करेगा।  2. `FileReader` के ज़रिए इमेज लोड होगी।  3. इमेज को एक हिडन HTML5 `<canvas>` पर ड्रा किया जाएगा।  4. Canvas पर ड्रा करने से सारा EXIF डेटा अपने आप हट जाता है।  5. `canvas.toBlob()` या `canvas.toDataURL()` से क्लीन इमेज एक्सपोर्ट करके डाउनलोड लिंक दी जाएगी।

## 3. UI/UX Components
- **Header:** ऐप का नाम और संक्षिप्त विवरण।
- **Upload Box:** ड्रैग-एंड-ड्रॉप ज़ोन और 'Choose Image' बटन।
- **Preview Section:** ओरिजिनल इमेज प्रीव्यू और इमेज का साइज।
- **Action Button:** 'Remove Metadata & Download' बटन।
- **Status Indicator:** प्रोसेस स्टेटस (Ready, Processing, Done)।

## 4. Step-by-Step Execution Plan
- [x] **Step 1:** प्रोजेक्ट रूट में `PLAN.md` सेव करना।
- [ ] **Step 2:** `preview.html` तैयार करना जिसमें आधुनिक रिस्पॉन्सिव लेआउट, सीएसएस स्टाइलिंग और कैनवास लॉजिक शामिल हो।
- [ ] **Step 3:** टर्मक्स/लोकल सर्वर पर टेस्ट करना और डाउनलोड की गई इमेज का मेटाडेटा चेक करना।
- [ ] **Step 4:** यदि यूजर "OK" कहे, तो `index.html` में शामिल करना।

## 5. File Structure
```
/root/exif-remover/
├── PLAN.md          # This implementation plan
├── index.html       # Main application file (will be created after approval)
└── preview.html     # Preview/working code (created first for review)
```