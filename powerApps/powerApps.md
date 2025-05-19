12.5.2025

-Create and add new feature:
    1.When a user registers a new item, the input form is displayed in order
    2.When new items are registered SharePoint file, developer will get notification through Power Automate.
    3.How to use the drop-down form in PowerApps
    4.PopUp window
    5.Export PowerApps data another account

13.5.2025

-PowerApps:
    -Improved stage management in PowerApps


-PowerAutomate:
    -Detect changes in personal information with Power Automate, update a PDF template, and send it

    -Automatically generate and send a PDF based on updated SharePoint data

    -When employee information is updated, generate and send a PDF via an automated flow

14.5.2025

-PowerApps:
    -How to manage state using Set() and other Power Apps functions

    -How to retrieve values from selection controls like Dropdown, Radio, and Toggle

    -Understanding the integration between Power Apps and SharePoint as a data source

    -Designing view/edit screens following proper and stable UI patterns

    -Developing a clear sense of UI-data consistency and user-driven interactions

-19.5.2025

# 📩 PowerApps × Power Automate – Event Creation & Mail Integration

This project integrates **Microsoft Power Apps** and **Power Automate** to build a mobile-friendly inventory app. It features UI state control, conditional navigation, and automated event creation via Outlook Calendar or mail functionality.

---

## ✅ Features

- 🎨 Power Apps UI with Gallery, Detail view, and Pop-up windows
- 📨 Conditional navigation to a **mail screen** via gallery icon
- 🔁 Input fields reset after form submission
- 📅 Power Automate flow for creating calendar events (Outlook)
- 🔗 Connected to SharePoint as the backend list

---

## 🧠 Architecture Overview

### Power Apps

| Feature | Description |
|--------|-------------|
| Gallery | Displays inventory list (SharePoint source) |
| Set / Context Variables | Used for controlling screen logic and UI flags |
| Conditional Navigation | Icon-based navigation to MailScreen, separate from item selection |
| Reset Inputs | After submission, text inputs are cleared using `Set(resetXYZ, true)` |
| Visual Feedback | Popups and warnings using `Notify(...)` and `UpdateContext(...)` |

### Power Automate

| Step | Action |
|------|--------|
| 1️⃣ | Triggered by Power Apps |
| 2️⃣ | Input parameters collected (subject, body, time, etc.) |
| 3️⃣ | Create event in Outlook Calendar (or send email) |
| ✅ | Status returned back to Power Apps |

---

## 🔁 Gallery Control Logic

```powerapps
// Gallery OnSelect
If(
    Not(varBypassGalleryClick),
    Set(selectedItem, ThisItem);
    Navigate(DetailScreen1, ScreenTransition.None)
)

🧾 Tips & Best Practices
Use Set() for global variables, UpdateContext() for screen-local logic

Use Refresh(DataSource) after editing SharePoint columns

Make use of Reset property in inputs for cleaner UX

Avoid hardcoding – rely on ThisItem and variables

Modularize repetitive popups via components