# Life RPG

**A gamified personal organisation app that turns everyday goals, routines, and progress into an RPG-style journey.**

Life RPG is an Android app that makes daily tasks more fun by turning them into a game. Create quests, finish them to earn XP and coins, keep your streak alive, unlock achievements, and watch your character level up.

> MAD (Mobile Application Development) course project  
> School of Technology Management and Engineering, NMIMS Chandigarh Campus

---

## Team

| Name | Roll No. |
|------|----------|
| Ashna | D026 |
| Reet | D009 |

**Submitted to:** Dr. Preetjot Kaur

---

## Features

**Core**
- **Registration and Login** – create an account, sign in, "Remember Me", and password recovery
- **Home Dashboard** – level, XP bar, streak, and quick access to every module
- **Quests** – create, edit, complete, and delete quests with category, difficulty, duration, and deadline (XP is awarded automatically)
- **Quest Roadmap** – quests shown as a visual path (completed / current / locked) with overall progress
- **Goal Tracker** – personal goals with category, deadline, and 0–100% progress

**Rewards and progression**
- **Daily and Weekly Challenges** – extra objectives for bonus coins
- **Achievements** – 38 trophies across quests, streaks, XP, coins, and difficulty
- **Progress History** – level, XP, quest totals, streaks, and recent activity
- **Coin Shop and Character Customisation** – spend coins on outfits and accessories, then equip them
- **Profile** – player identity, XP, coins, and character stats (Intelligence, Strength, Health, Discipline, Creativity)

**Planning and personal space**
- **Life Calendar** – events by date with reminders and notifications
- **Knowledge Vault** – save notes by category, search them, star favourites, mark as learned
- **Life Map** – save meaningful places on a Google Map
- **Life Gallery / My Files** – keep documents, pictures, and study material in one place
- **Data Export** – export your data as a readable TXT file or as CSV files packed in a ZIP

---

## Tech Stack

| Area | Details |
|------|---------|
| Platform | Android (minSdk 24, targetSdk 36) |
| Language | Java 11 |
| UI | XML layouts |
| Database | SQLite (via `DatabaseHelper`) |
| IDE | Android Studio |
| Maps | Google Maps SDK + Places SDK |
| Export | Android Storage Access Framework (TXT / CSV in ZIP) |

---

## Getting Started

### Prerequisites
- Android Studio (latest stable)
- Android SDK 36 installed
- An Android emulator or a physical device (Android 7.0 / API 24 or higher)

### Run the app
1. Download `mad.zip` from this repository and unzip it.
2. Open the unzipped project folder in Android Studio.
3. Wait for Gradle sync to finish.
4. Add your own Google Maps API key (needed for the Life Map screen). In `app/src/main/res/values/strings.xml`:
   ```xml
   <string name="google_maps_key">YOUR_API_KEY_HERE</string>
   ```
5. Press **Run** and pick an emulator or device.

> The API key has been removed from the submitted code on purpose. The app works without it, but the Life Map screen will show a blank map.

### Permissions used
- `POST_NOTIFICATIONS` – calendar reminders
- `SCHEDULE_EXACT_ALARM` – reminders at the exact time you set

---

## How Data Is Stored

- All user data (accounts, quests, goals, achievements, notes, places, etc.) is stored **locally** in SQLite through `DatabaseHelper.java`.
- Each screen is its own Activity, and activities pass identifiers to each other so every screen shows data for the logged-in user.
- User input is validated before it is saved, to avoid empty or incorrect entries.
- Export uses the Storage Access Framework so the user picks where the file is saved.

---

## Project Structure

The source code is inside `mad.zip`. Layout of the app module:

```
app/src/main/
├── java/com/example/mad/
│   ├── MainActivity.java        # Login
│   ├── register.java            # Sign up
│   ├── forgot_password.java     # Password recovery
│   ├── home.java                # Dashboard
│   ├── quest*.java              # Quest create / view / details
│   ├── roadmap.java             # Quest roadmap
│   ├── goal_tracker.java        # Goals
│   ├── challenges.java          # Daily and weekly challenges
│   ├── achievement.java         # Trophies
│   ├── progress.java            # Progress history
│   ├── shop.java, ShopAdapter.java
│   ├── customization.java, CustomizationAdapter.java
│   ├── profile.java             # Character and stats
│   ├── calender.java            # Calendar and reminders
│   ├── NotificationHelper.java, NotificationReceiver.java
│   ├── knowledge.java           # Knowledge Vault
│   ├── lifemap.java             # Life Map
│   ├── filehandling.java        # Life Gallery / My Files
│   ├── data_export.java         # TXT / CSV export
│   └── DatabaseHelper.java      # SQLite helper
└── res/
    ├── layout/                  # XML screens
    └── drawable/                # Images and icons
```

---

## Submission Files

| File | What it is |
|------|------------|
| [`mad.zip`](mad.zip) | Zipped Android Studio project (source code) |
| [`Ashna_Reet_MADProjectReport_LifeRPG.pdf`](Ashna_Reet_MADProjectReport_LifeRPG.pdf) / [`.docx`](Ashna_Reet_MADProjectReport_LifeRPG.docx) | Project report |
| [`Ashna_Reet_MADProjectPpt_LifeRPG.pptx`](Ashna_Reet_MADProjectPpt_LifeRPG.pptx) | Project presentation |
| [`Ashna_Reet_MADProjectVideo_LideRPG.mp4`](Ashna_Reet_MADProjectVideo_LideRPG.mp4) | Working demo video |

---

## Future Scope
- More customisation options
- Further improvements to the overall user experience

---

## Acknowledgement

Thanks to our faculty guide, Dr. Preetjot Kaur, for her guidance throughout this project, and to NMIMS Chandigarh for the opportunity to build it as part of the Mobile Application Development course.
