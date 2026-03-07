# PEPSI WORDL'D 🥤

A Pepsi-branded Wordle game for PepsiCo conference attendees.  
Built on the classic Wordle mechanic — guess the 5-letter word in 6 tries.

**Live game:** https://smassietech.github.io/pepsi-wordld/

---

## 📁 Files

| File | What it does |
|---|---|
| `index.html` | The game itself — you rarely need to touch this |
| `puzzles.json` | **The puzzle schedule — edit this to update words & hints** |

---

## ✏️ How to update the puzzle schedule

You can do this entirely in the GitHub website — no code editor needed.

1. Go to your repo: https://github.com/smassietech/pepsi-wordld
2. Click **`puzzles.json`**
3. Click the **pencil ✏️ icon** (top right of the file view) to edit
4. Add, remove or change puzzle entries — each one looks like this:

```json
{
  "num": 85,
  "date": "2026-05-31",
  "word": "CRISP",
  "hint": "Thin, crunchy, salted potato snack 🥔",
  "partial": ""
}
```

**Field guide:**

| Field | Required | Notes |
|---|---|---|
| `num` | ✅ | Puzzle number — must be unique, sequential |
| `date` | ✅ | Format: `YYYY-MM-DD`. Game auto-selects today's puzzle by this date |
| `word` | ✅ | Exactly 5 capital letters. Must be a real word from the allowed list |
| `hint` | ✅ | Shown to players above the board as a clue. Emojis are fine! |
| `partial` | ✅ | Leave as `""` if the word is complete. Use `"Partial: short for X"` if it's an abbreviation |

5. Click **Commit changes** (green button, bottom of page)
6. Game updates automatically within ~60 seconds ✅

---

## 🗓️ Puzzle schedule rules

- The game shows today's puzzle based on the **`date`** field — no admin action needed
- If today's date isn't in the list, it cycles back to the beginning
- Dates don't have to be consecutive — you can skip weekends, add doubles, etc.
- The **admin panel** (⚙ gear icon in the game) shows the full schedule and lets you override for testing

---

## 🔧 Admin panel

Click the ⚙ gear icon in the top-right of the game to:
- Override the word and puzzle number for testing
- View the full puzzle schedule with dates, hints, and today's puzzle highlighted
- Set up the Firebase leaderboard URL

---

## 🏆 Leaderboard (Firebase)

The leaderboard requires a free Firebase Realtime Database:

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Create a project → Realtime Database → **Test Mode**
3. Copy your database URL (e.g. `https://your-project-default-rtdb.firebaseio.com/`)
4. Paste it into the game's ⚙ admin panel → **Firebase URL** field

---

## 🚀 Sharing with attendees

Share this URL:
```
https://smassietech.github.io/pepsi-wordld/
```

Or generate a puzzle-specific link from the ⚙ admin panel using **"Generate Shareable Link"**.

---

## 📋 Current puzzle list

See [`puzzles.json`](./puzzles.json) for the full schedule.  
84 puzzles covering PepsiCo beverages, international snacks, UK crisps, and Finance & Controls vocabulary.
