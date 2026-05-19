# Privacy Policy for DateMind

**Last Updated:** May 19, 2026  
**Effective Date:** May 18, 2026

## 1. Overview

DateMind ("**we**," "**us**," "**our**," or "**the app**") is a voice-first calendar app that uses artificial intelligence to help you create and manage events. This Privacy Policy explains how we collect, use, store, and protect your information.

**Key principle:** We minimize data collection. Calendar events and speech are processed locally on your device whenever possible. Cloud storage is only used when you explicitly sync or sign in.

---

## 2. What Information We Collect

### 2.1 Information You Provide

**Google Account Sign-In**
- Email address, full name, and profile picture
- Stored locally on your device; used only for cloud sync and API authentication
- Not shared with third parties

**Calendar & Event Data**
- Event titles, dates, times, locations, descriptions, and categories
- Shared only with your device's calendar app (if you choose "Sync to calendar")
- Stored locally in DateMind's app database

**Event Reminders**
- Reminder times and notification preferences
- Stored locally only

**Custom Categories**
- Category names you create
- Stored locally and synced to cloud (if signed in)

### 2.2 Information Collected Automatically

**Speech & Text Input**
- **On-device processing:** Your speech is converted to text using on-device speech recognition (Expo Speech Recognition). No audio files are sent to us.
- **Transcribed text:** The text transcription is sent to our backend only when you ask the AI to process it (e.g., "parse this event" or chat with the assistant)
- **AI processing:** Your transcribed event text is sent to OpenAI's servers to extract structured event data. See [OpenAI's Privacy Policy](https://openai.com/privacy/) for their handling.

**Usage Analytics**
- Number of AI requests per day (counted for quota enforcement only)
- Error logs (to debug issues)
- Timestamps of API calls
- Not tied to individual events; aggregated only

**Device Information**
- Device model, OS version, app version
- Timezone and locale (to process dates correctly)
- Only sent when you use cloud sync or AI features

---

## 3. How We Use Your Information

| Purpose | Data Used | Location |
|---------|-----------|----------|
| **Create events from voice/text** | Transcribed text | Sent to OpenAI; deleted from their servers per [OpenAI retention policy](https://openai.com/api/policies/service-terms/) |
| **Sync to device calendar** | Event data | Passed to device calendar provider (Google, Apple, Samsung, etc.) |
| **Cloud sync (when signed in)** | Events, categories, settings, profile name | Stored in our cloud database (Fly.io Postgres) |
| **Enforce daily AI quota** | Request count per day | Stored in cloud database |
| **Debug & improve the app** | Error logs, usage patterns | Stored in cloud logs; retained for 30 days |
| **Authenticate your account** | Google idToken (JWT) | Verified but not stored; discarded after use |

---

## 4. Where Your Data Is Stored

### 4.1 Local Storage (Device)
- **Encrypted:** Stored in SQLite on your device (not encrypted by default; depends on device OS)
- **Content:** All events, categories, reminders, preferences
- **Accessible:** Only by DateMind app and your device's calendar system
- **Ownership:** You own this data; it never leaves your device unless you:
  1. Sign in and enable cloud sync
  2. Use AI features (sends text to OpenAI)
  3. Share events with others via share code

### 4.2 Cloud Storage (Optional)
- **Provider:** Fly.io (PostgreSQL database in Ireland)
- **Content:** Events, categories, custom settings (only if you're signed in)
- **Encryption:** HTTPS in transit; encrypted at rest (Fly.io default)
- **Retention:** Kept until you delete your account or disable sync

### 4.3 Third-Party Services
| Service | What We Share | Purpose | Link |
|---------|---------------|---------|------|
| **OpenAI** | Transcribed event text | AI event parsing & chat | [Privacy](https://openai.com/privacy/) |
| **Google** | Your email, idToken | Authentication & calendar sync | [Privacy](https://policies.google.com/privacy) |
| **Fly.io** | Encrypted event data | Cloud database hosting | [Privacy](https://fly.io/legal/privacy-policy/) |

---

## 5. Data Retention

| Data Type | Retention | Notes |
|-----------|-----------|-------|
| **Local events** | Until you delete | Stored on your device indefinitely |
| **Cloud events (synced)** | Until deletion or account removal | Removed from cloud when deleted in-app |
| **Speech audio** | 0 days (not stored) | Converted to text on-device, never stored |
| **Transcribed text sent to OpenAI** | Per OpenAI policy (~30 days) | See [OpenAI retention](https://openai.com/api/policies/service-terms/) |
| **Usage logs (quota tracking)** | 30 days | Aggregated; not tied to individual events |
| **Error logs** | 30 days | Deleted automatically |
| **Google account info** | Until you sign out | Stored locally in app settings |

---

## 6. Sharing & Sharing Codes

When you share events with others:
- **Share Code:** A 7-character code is generated and stored in our cloud database
- **Code Expiration:** Codes expire after 30 days (or when you revoke)
- **Who Can Access:** Anyone with the code can import your events (no Google sign-in required)
- **Already-imported copies:** If someone imports your events and you later revoke the code, their local copy is NOT deleted
- **Privacy:** Share codes are not linked to your email; they're anonymous unless you tell the recipient your name

**To prevent unauthorized access:** Treat share codes like passwords. Don't post them publicly.

---

## 7. Your Rights & Control

### 7.1 Access Your Data
- All your events, categories, and settings are visible in the app
- You can export event data (manually copy from Events tab)

### 7.2 Delete Your Data
**Local deletion:**
- Delete individual events in the app
- Clear all app data via Android Settings → Apps → DateMind → Storage → Clear Data

**Cloud deletion:**
- Events are synced to cloud only if you're signed in
- In-app full deletion: Settings → Delete my account and data
- The in-app delete action removes your cloud data tied to your signed-in account and signs you out
- You can also contact us to request full account deletion (see **Contact** section)

**Deletion timing:**
- Cloud data is removed from our primary database as part of the account deletion flow
- Encrypted backup copies may persist for a limited period based on infrastructure backup rotation

**Third-party deletion:**
- To delete your Google account: [Google Account deletion](https://support.google.com/accounts/answer/8313285)
- To request OpenAI delete your data: [OpenAI deletion request](https://openai.com/contact/)

### 7.3 Opt Out of Cloud Sync
- Disable "Cloud sync" in Settings
- Events remain local only; nothing synced to our servers
- Already-synced events are not deleted from cloud until you sign out

### 7.4 Disable AI Features
- You can manually add events without using the AI
- AI requests count toward your daily quota; manual events do not

---

## 8. Children's Privacy

DateMind does not knowingly collect personal information from children under 13. If we discover we have collected data from a child under 13 without parental consent, we will delete it immediately. For COPPA compliance, parents/guardians can contact us to request deletion.

---

## 9. Security & Encryption

- **Transmission:** All communication between the app and our servers uses HTTPS (TLS 1.2+)
- **Storage:** Cloud data is encrypted at rest in our Fly.io database
- **Local data:** Depends on your device's storage encryption (enable it in Android Settings)
- **Access control:** Only you can access your cloud data (authenticated by Google)
- **Backups:** Fly.io maintains automated backups; these are also encrypted

**What we don't do:**
- We don't sell your data
- We don't use your data for advertising
- We don't share your events with marketers
- We don't use machine learning to profile you outside the app

---

## 10. Changes to This Policy

We may update this policy as the app evolves (e.g., new features, legal requirements). Changes will be noted with an updated "Last Updated" date above. Significant changes will be announced in the app. Continued use of the app after updates means you accept the new policy.

---

## 11. Contact & Data Requests

For privacy questions, data deletion requests, or to report a security issue:

**Email:** joniprodev@gmail.com  
**Response time:** 7 business days

Include:
- Your Google email (if signed in)
- Description of your request
- Any relevant dates or event details

**European Users (GDPR):**
If you're in the EU, you have the right to:
- Access your data
- Correct inaccurate data
- Delete your data ("right to be forgotten")
- Data portability
- Withdraw consent

Email us with "GDPR Request" in the subject line.

---

## 12. Third-Party Links

This policy does not cover third-party services linked in the app (e.g., Google, OpenAI, license websites). Review their privacy policies separately.

---

## Appendix: Quick Reference

**My data is local only if I:**
- Don't sign in to Google ✓
- Don't enable "Cloud sync" ✓
- Only manually add events ✓

**My data goes to OpenAI when I:**
- Ask the AI to parse an event ✓
- Chat with the assistant ✓

**My data goes to the cloud when I:**
- Sign in to Google ✓
- Enable "Cloud sync" ✓
- Create a share code ✓

**My synced cloud data is deleted when I:**
- Use "Delete my account and data" in Settings while signed in ✓

---

**DateMind Privacy Policy v1.1**  
Transparent, minimal data collection. Your calendar, your control.
