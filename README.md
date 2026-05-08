# ClawSight: Autonomous On-Device Intelligence Agent

ClawSight is a privacy-first, autonomous background agent for Android. It bridges the gap between raw device context and actionable intelligence by monitoring communication (WhatsApp, Telegram, Gmail) and visual data (Screenshots, Downloads) to automatically decipher and organize your digital life.

---

## External Resources and Links

Due to repository size constraints and the necessity of high-fidelity assets for evaluation, the primary project files are hosted on Google Drive. **Please ensure you are logged into a Google account to access these links.**

* **Complete Source Code (Android Project):** https://drive.google.com/drive/folders/1CaZnT8L_1Ib-RlzhY87IeRNGvMRMKtjx?usp=sharing
* **Project Demo Video (Walkthrough):** https://drive.google.com/drive/folders/1pLybJX78Y2UwPIp5e303rPCHd2hY_qTU?usp=sharing
* **Compiled APK (ClawSight.apk):** https://drive.google.com/drive/folders/1DdNiBG5Gh8K7rBmwxD83rhnsoJtblfVh?usp=sharing
* **Gemma LLM Model (gemma2b-it-cpu-int4.bin):** https://drive.google.com/drive/folders/1VhECYRnNM0M8nbVuAqUi_SqFfA4XPxd-?usp=sharing

---

## Repository Structure

| Item | Type | Description |
| --- | --- | --- |
| **`ClawSight_AI_Disclosure.docx`** | File | Detailed breakdown of AI feature origins and tool usage. |
| **`ClawSight_Presentation.pptx`** | File | Professional slide deck explaining the architecture and vision. |
| **`README.md`** | File | Project documentation, tech stack overview, and setup guide. |

---

## Problem and Solution

* **The Problem:** Users are overwhelmed by digital fragmentation and the privacy risks of sending sensitive PII to cloud-based AI.
* **The Solution:** A 100% on-device Sight-to-Action pipeline that scrubs data and generates actions locally.

---

## The Sight-to-Action Pipeline

1. **Detection:** Monitors MediaStore (Images) and Notifications (WhatsApp/Gmail).
2. **OCR:** Google ML Kit extracts text locally.
3. **Privacy:** Regex-based Hard Gate scrubs phone numbers and emails before AI inference.
4. **Intelligence:** Gemma 2B IT (int4) categorizes context and extracts action items.
5. **Action:** Automatically triggers Android Calendar events and Google Tasks.

---

## The Tech Stack

* **Intelligence:** MediaPipe Tasks-GenAI and Gemma 2B IT.
* **Vision:** Google ML Kit.
* **Memory:** Room Persistence Library (SQLite).
* **Architecture:** Kotlin Coroutines, Channels, and Android Jetpack.

---

## Setup and Usage Instructions

### Running the Source Code

1. Download the Source Code zip from the Google Drive link above and extract it.
2. Download the `gemma2b-it-cpu-int4.bin` model file and place it in the `app/src/main/assets/` directory of the extracted project.
3. Open the folder in Android Studio and click Run.

### Installing the APK Directly

1. Download the `ClawSight.apk` from the Google Drive link provided above.
2. Enable Install from Unknown Sources in your Android device settings.
3. Install and launch the app.
4. **Grant Permissions:** You MUST enable Notification Access and Media Permissions for the agent to function.

---

## Privacy and Performance

* **100% Air-Gapped:** The application contains no network upload logic; it is 100% local.
* **Hardware-Aware:** Automatically detects CPU architecture and adjusts power usage to prevent lag.
* **Event-Driven:** Minimized battery drain by avoiding constant polling or background scanning.

---

## AI Disclosure

* **Models:** Gemma 2B IT and Google ML Kit.
* **Assistance:** Gemini (Android Studio) was utilized to optimize PII Redaction Regex, architect the background ClawSightService, and draft the Room Database schema.

  ---

  * ""Since we were not able to upload files larger than 100MB to github, we have provided the drive links for each.""
