# HIIT Timer Privacy Overview

This document provides a clear, plain-English summary of the data practices within the HIIT Timer application.

Our guiding principle is **Privacy by Design**. We collect the absolute minimum data necessary to provide our features, and your most sensitive data (HealthKit) **never leaves your device**.

## Data Handling Summary

---

### Health Data
*(VO2 Max, RHR, Age, Sex)*

**Where It's Processed & Stored:**
**On-Device ONLY.** It is *never* stored, collected, or transmitted by us.

**Why We Need It:**
**(Read-Only)** To calculate your "Cardio Age" locally on your phone.

### Anonymous Analytics
*(e.g., "screen_viewed", "timer_started")*

**Where It's Processed & Stored:**
**Sent to PostHog** (our analytics provider). This is not linked to your personal identity.

**Why We Need It:**
To understand which features are used, fix bugs, and improve the app. **This is optional and can be disabled.**

### App Settings & History
*(e.g., Timer settings, recent workouts)*

**Where It's Processed & Stored:**
**Locally on your device** (`UserDefaults`). This data may be part of your encrypted device backups (e.g., iCloud).

**Why We Need It:**
To save your preferences and provide the "Recent Workouts" list for your convenience.

### Active Timer State
*(e.g., current round, time remaining)*

**Where It's Processed & Stored:**
**Locally on your device** (`UserDefaults`). This is automatically deleted when your workout is complete.

**Why We Need It:**
To restore an active timer session if you close the app or your phone restarts.

---

## 1. HealthKit Data (Your Most Sensitive Data)

Our "Cardio Age" feature requires **read-only** permission to your Apple Health data.

We read: Date of Birth, Biological Sex, VO2 Max, and Resting Heart Rate.

We **DO NOT** Write: The app does not write any data to your HealthKit store.

**ON-DEVICE PROCESSING:** All calculations are performed *only* on your device.

**WE NEVER SEE IT:** Your personal health data is **never** sent to our servers, never included in analytics, and never shared with any third party. We have actively designed the app to exclude it from all tracking.

Your HealthKit data remains private to you, as it should be.

## 2. Anonymous Analytics (How We Improve the App)

To understand how our app is performing, we use **PostHog** for anonymous analytics.

**What We Track:** We track anonymous events like which buttons are tapped or which screens are viewed. We **do not** track your personal health data, your age, your VO2 Max, or your specific timer settings.

**"Tracking" vs. "Anonymous":** We use a random, anonymous ID to see if a bug is affecting one person or many. Because this ID is "persistent" (stored on your device), Apple's App Store guidelines require us to declare this as "Tracking". This ID is **never** used to track you across other apps or websites and is **not linked to your personal identity**.

**Your Control:** You have two levels of control. First, you can **Opt-Out** of all anonymous analytics at any time in the app's "Settings" menu. Second, you can **Reset (Right to Erasure)** your analytics ID from the Settings menu. This deletes your old ID and creates a new one, effectively erasing your past analytics history.

## 3. Local Data (Your Settings & History)

The app saves your settings and workout history on your device for your convenience.

**What is saved:** Your preferred work/rest/round settings, sound/haptic preferences, and a list of your 20 most recent unique workouts.

**Where it is:** This data is stored in your app's local `UserDefaults` file. It **never** leaves your device, though it may be included in your private, encrypted iCloud or computer backups.

**Active Timers:** If you are in the middle of a workout, the app saves your current state (e.g., "Round 2, 01:30 left") so you can resume if the app quits. This file is automatically deleted when your workout is finished.

## 4. Security

We take your privacy seriously. The app's API keys for analytics are not stored in the source code but are in a file that is excluded from our Git repository to prevent exposure. We have also conducted a security review to identify and remediate critical issues.

### Questions?

If you have any questions about our privacy practices, please contact us at **[Your Support Email Here]**.