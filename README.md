# Cardboard Box ATM — Tablet + Telegram Bot Guide

Everything runs inside a single standalone file: [`index.html`](./index.html). No server or installation is needed.

---

## 1. Create Your Telegram Bot (Takes 60 Seconds)
1. Open Telegram on your phone and search for **[@BotFather](https://t.me/BotFather)**.
2. Send `/newbot` and follow the prompts:
   - Give your bot a name (e.g., `School ATM Bot`).
   - Give it a username ending in `bot` (e.g., `mustafa_school_atm_bot`).
3. **@BotFather** will give you an **HTTP API Token** (looks like `1234567890:ABCdefGhIJKlmNoPQRsTUVwxyZ`). Copy it!

---

## 2. Connect the Tablet to the Telegram Bot
1. Open [`index.html`](./index.html) in Chrome/Safari/Edge on the **tablet** mounted on the ATM box.
2. Tap the **`$` bank icon** (top-left) or the **status badge** (top-right) on the screen to open the hidden Operator Setup menu.
3. Paste your **Telegram Bot Token** and tap **Save & Connect**.
4. Tap **⛶ Fullscreen** inside that menu (or tap the digital clock in the top-right corner) so the display fills 100% of the tablet screen.
5. On the phone inside the ATM box, open your new Telegram bot and send `/start` (or any message).
   - The tablet will automatically detect the kid's **Chat ID**, turn the status light **GREEN (`ONLINE`)**, and send the kid an interactive ATM Operator menu on Telegram!

---

## 3. How a Transaction Works (Step-by-Step)

1. **Card Inserted**:
   - Customer slides their paper/plastic card into the box slot.
   - The kid inside reads the name on the card and **types the name into the Telegram bot** (or taps one of the preset account buttons in Telegram).
   - *(If it's a brand-new name, the ATM automatically creates an account for them with `$500` default balance!)*
2. **Language Selection (`EN` / `RO` / `RU`)**:
   - The tablet greets the cardholder by name and prompts them to choose **English**, **Română**, or **Русский** (by tapping either the on-screen ATM button or the physical-style `L1–L4` / `R1–R4` side keys).
3. **4-Digit PIN**:
   - Customer enters any 4 digits on the ATM keypad (can also be turned off in `⚙ OPERATOR`).
4. **Main ATM Menu**:
   - **Withdraw Cash**:
     - Customer picks `$20`, `$50`, `$100`, `$200`, `$500`, or types a custom amount.
     - Tablet displays `"PREPARING YOUR CASH..."` with a bill-counting animation.
     - Kid inside immediately gets a Telegram alert: `🚨 WITHDRAWAL REQUEST: $100`.
     - Kid counts `$100`, pushes it through the cash slot, and taps **`✅ DONE — Dispensed $100`** (or types `done`) in Telegram.
     - Tablet chimes, deducts `$100` from the account balance, and stays on the **"PLEASE TAKE YOUR CASH & CARD"** screen (with a periodic ATM reminder beep).
     - The kid pushes the card out of the slot, waits for the customer to take it from their hand, and taps **`👋 Card Was Taken From My Hand`** in Telegram to return the tablet to the Welcome screen!
   - **Deposit Cash**:
     - Customer chooses **Deposit Cash** and inserts bills into the slot.
     - Kid inside counts the cash and either taps a quick button (`+$10`, `+$20`, `+$50`, `+$100`, `+$200`, `+$500`) or **types the exact number** (e.g., `75`) in Telegram.
     - Tablet adds the amount to the customer's balance and stays on **"PLEASE TAKE YOUR CARD"** until the kid taps **`👋 Card Was Taken From My Hand`** in Telegram!
   - **Display Balance**:
     - Displays the customer's current balance on screen.

---

## Useful Telegram Commands for the Kid Inside the Box
- **Type any name** (e.g., `Mustafa` or `Alex`) → Logs that cardholder in on the tablet immediately.
- **`done`** (or tap the `✅ DONE` button) → Completes a withdrawal after pushing cash out.
- **Type a number** during Deposit (e.g., `100`) → Credits that deposit amount and finishes the transaction.
- **`Alex=1000`** → Sets `Alex`'s balance to `$1000` on the fly.
- **`/menu`** or **`/start`** → Shows all clickable account buttons in Telegram.
- **`/reset`** → Resets the tablet back to the "Please Insert Your Card" welcome screen.
