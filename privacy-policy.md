# Privacy Policy — Gaia AutoFill Chrome Extension

**Effective Date:** October 13, 2026
**Last Updated:** October 13, 2026
**Version:** 2.0

---

> **Tóm tắt nhanh:** Gaia AutoFill không thu thập, không lưu trữ và không truyền bất kỳ thông tin cá nhân nào của người dùng ra bên ngoài thiết bị. Tiện ích chỉ lưu dữ liệu sĩ số lớp học cục bộ trên máy bạn và đọc lịch dạy từ nguồn GitHub công khai.

---

## 1. Introduction / Giới Thiệu

**Gaia AutoFill** ("the Extension", "we", "our") is a Chrome browser extension developed to assist teachers at **Gaia Education Center, Dong Nai Region, Vietnam**, in automatically filling electronic teaching report forms (Google Forms) based on their scheduled teaching timetables.

This Privacy Policy describes:
- What data the Extension accesses, collects, stores, or transmits
- How and why each browser permission is used
- Your rights regarding any locally stored data
- How to contact us with privacy-related questions

By installing and using Gaia AutoFill, you agree to the practices described in this Privacy Policy.

---

## 2. Information We Do NOT Collect

Gaia AutoFill is designed with a **privacy-first approach**. We explicitly **do not**:

- ❌ Collect, store, or transmit your name, email address, phone number, or any personally identifiable information (PII)
- ❌ Track your browsing history, visited URLs, or web activity
- ❌ Access the content of any web pages other than the Google Forms teaching report page you are actively filling
- ❌ Use cookies, fingerprinting, analytics SDKs, or any third-party tracking tools
- ❌ Send any user data to our servers (we operate no backend server)
- ❌ Share any data with advertisers, data brokers, or any third parties
- ❌ Execute remote code — all logic is bundled locally within the extension package

---

## 3. Data the Extension Accesses

### 3.1 Data Read from External Sources (Read-Only)

The Extension fetches the following **publicly available, non-personal** data from GitHub:

| Source | Data Retrieved | Contains Personal Info? |
|---|---|---|
| `raw.githubusercontent.com/PDN237/Data_Gaia_DN/main/Data/` | Weekly teaching timetable (JSON) — class names, lesson periods, time slots, subject names | ❌ No personal data |
| `raw.githubusercontent.com/PDN237/Data_Gaia_DN/main/Data/form.json` | Form field configuration — field aliases, required fields, default values | ❌ No personal data |
| `raw.githubusercontent.com/PDN237/Data_Gaia_DN/main/Data/class.json` | Class registry — class names and their associated school | ❌ No personal data |
| `api.github.com` | Metadata check to verify the latest version of timetable data | ❌ No personal data |

These requests are **one-way reads**. No data from your device is sent to GitHub in the body of these requests beyond standard HTTP headers (IP address, browser User-Agent) handled entirely by your browser and GitHub's infrastructure, subject to [GitHub's own Privacy Policy](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

### 3.2 Data Stored Locally on Your Device

The Extension stores the following data **exclusively on your local device** using the Chrome browser's built-in `chrome.storage.local` API:

| Data Stored | Example | Purpose | Sent Externally? |
|---|---|---|---|
| Class enrollment count per school | `{ "school": "Trường ABC", "class": "Lớp 5A", "siSo": 35 }` | Auto-populate class size field in future teaching reports to save re-entry | ❌ Never |

**Key facts about this local storage:**
- Stored data **never leaves your device**
- It is **isolated to this extension only** — no website or other extension can access it
- It contains **no personally identifiable information** — only class name, school name, and enrollment numbers (institutional data, not personal)
- You can delete it at any time (see Section 7)

### 3.3 Data Written to Google Forms (On-Device Only)

When you trigger the auto-fill action, the Extension reads data from the local timetable and writes it into the fields of the Google Forms teaching report tab that **you have already opened**. This action:

- Happens **entirely within your browser**, on a tab you opened
- Does **not** transmit data to any server controlled by us
- Fills only the specific Google Form you are actively using
- Is subject to [Google's Privacy Policy](https://policies.google.com/privacy) once you submit the form

---

## 4. Browser Permissions Explained

Gaia AutoFill requests the following Chrome permissions. Each permission is used exclusively for the stated purpose:

### `storage`
**Why needed:** To save class enrollment counts (`chrome.storage.local`) on your local device so you don't need to re-enter class sizes every time you submit a teaching report.  
**What it does NOT do:** Does not read or write browser cookies, bookmarks, passwords, or any data beyond the class-size records described above.

### `activeTab`
**Why needed:** To read the URL of the tab you are currently viewing, in order to confirm it is a Gaia teaching report Google Form before attempting to fill it.  
**What it does NOT do:** Does not access tab content, page text, or any other browsing data. Only activates when you click the Extension button.

### `scripting`
**Why needed:** To inject the `content.js` script into the Google Forms tab you have opened, enabling the Extension to programmatically fill in the form fields (teacher ID, date, class, lesson info, enrollment count, etc.).  
**What it does NOT do:** Does not inject scripts into any other websites. Injection is limited to `https://docs.google.com/forms/*` only.

### `tabs`
**Why needed:** To identify which open browser tab is showing the teaching report Google Form, so the Extension can send the auto-fill data to the correct tab.  
**What it does NOT do:** Does not read tab titles, page content, or browsing history of any tabs.

---

## 5. Host Permissions Explained

The Extension declares access to the following domains. Access is **strictly limited** to the stated purposes:

| Domain | Purpose |
|---|---|
| `https://docs.google.com/*` | Read the structure of the Google Forms teaching report page and write data into its fields |
| `https://*.googleusercontent.com/*` | Load static assets (images, scripts) served by Google that are part of the Google Forms page |
| `https://raw.githubusercontent.com/*` | Fetch timetable data (JSON files) from the public Gaia GitHub repository |
| `https://api.github.com/*` | Check for the latest version of timetable data files |
| `https://forms.gle/*` | Handle shortened Google Forms links that redirect to `docs.google.com` |

The Extension **does not access** any other domains beyond those listed above.

---

## 6. Remote Code Policy

**Gaia AutoFill does not use remote code execution.**

All JavaScript logic is bundled within the Extension package installed on your device (`content.js`, `controler.js`, `backgroup.js`). Data fetched from GitHub (`.json` files) is **static configuration data** — it is never executed as code. This complies with Chrome Web Store's remote code policy.

---

## 7. Data Retention & Your Rights

### Locally Stored Data
The class enrollment data stored by the Extension remains on your device until you delete it. To remove all data stored by Gaia AutoFill:

1. Open Chrome and navigate to `chrome://settings/`
2. Go to **Privacy and security → Site settings → View permissions and data stored across sites**
3. Search for `Gaia AutoFill` and select **Delete**

Alternatively, uninstalling the Extension will remove all locally stored data.

### Data on Google Forms
Once you submit a teaching report form, that data is governed by Google's terms and your organization's (Gaia Center's) policies. The Extension has no control over data after submission.

---

## 8. Children's Privacy

Gaia AutoFill is designed exclusively for use by adult teachers at Gaia Education Center. It is not directed at, and does not knowingly collect any information from, individuals under the age of 13 (or the applicable minimum age in your jurisdiction).

---

## 9. Changes to This Privacy Policy

We may update this Privacy Policy from time to time to reflect changes in the Extension's functionality or legal requirements. When we do:

- The **"Last Updated"** date at the top of this page will be revised
- Significant changes will be noted in the Extension's update changelog on the Chrome Web Store

Continued use of the Extension after changes constitutes acceptance of the revised policy.

---

## 10. Governing Law

This Privacy Policy is governed by the laws of the **Socialist Republic of Vietnam**. Any disputes shall be resolved under Vietnamese jurisdiction.

---

## 11. Contact

If you have any questions, concerns, or requests regarding this Privacy Policy or the data practices of Gaia AutoFill, please contact:

- **Developer / Nhà phát triển:** Trung tâm Gaia — Khu vực Đồng Nai
- **Email:** binbkhoa123@gmail.com
- **GitHub:** [PDN237/Data_Gaia_DN](https://github.com/PDN237/Data_Gaia_DN)

We will respond to privacy-related inquiries within **5 business days**.

---

*This Privacy Policy applies solely to the Gaia AutoFill Chrome Extension and does not cover any other services or products of Gaia Education Center.*
