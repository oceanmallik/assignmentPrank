# 📄 assignmentPrank

> A realistic, hilarious university assignment paywall prank to troll friends who ask for your assignments at the last minute! 😂

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)]()
[![Platform](https://img.shields.io/badge/platform-Mobile%20%7C%20Desktop-blue.svg)]()

---

## 🎯 The Idea

Every semester, friends and classmates flood your WhatsApp/Messenger:
> *"Bro, assignment ta de na please!"* *(Bro, give me the assignment please!)*

Instead of arguing or giving it away for free, send them this link! When they open it, they think they've hit the jackpot with your submitted document—until they scroll down and realize the answers are locked behind a **5,000 Taka Bangla QR payment gate**.

---

## ✨ Features

- **Realistic PDF Viewer Interface**: Styled after Google Drive and Chrome's built-in PDF viewer with document details (`assignment.pdf`), page count, zoom controls, print, and download actions.
- **Progressive Blur (Scribd / CourseHero Style)**:
  - The top half of the assignment is crisp, authentic, and completely legible.
  - Starting midway down, the document smoothly and progressively blurs out using layered CSS gradient masks (`blur(6px)` transitioning to `blur(16px)` + frosted glass overlay).
- **Interactive Unlock Card**: Positioned right at the blur boundary with a clean call-to-action to unlock the full document.
- **5,000 ৳ Bangla QR Payment Modal**:
  - Pops up whenever they click *Unlock*, *Download PDF*, *Print*, or the blurred continuation pages.
  - Displays a real **Bangla QR Code** (`banglaQR.jpg`) with an animated laser scanner.
  - Supports payment badges for **bKash**, **Nagad**, and **Bangla QR / Any Bank**.
- **Simulated Transaction Verification**:
  - Lets friends type in a fake Transaction ID (TrxID).
  - Simulates a realistic 3-step banking validation ("Connecting to Bangladesh Bank...", "Checking MFS ledger...").
  - Triggers a buzzer sound and fails with **`Error 402: 0 TAKA DETECTED!`**.
- **Hilarious Troll Options**:
  - **😭 Bhai I'm Broke**: Automatically rejects mercy requests (reminds them of that 300 Tk cold coffee yesterday).
  - **🍗 1 Plate Biryani Offer**: Activates the Biryani protocol (1 Plate Kacchi + Cold Borhani trade offer).
  - **💬 Beg on WhatsApp**: Opens WhatsApp with a prefilled begging message directly to you.
- **Synthesized Audio Effects**: Uses the browser's native **Web Audio API** for buzzers and success chimes—zero external audio files needed!
- **Easter Egg Prank Reveal**:
  - Click the document title (`assignment.pdf`) 5 times, or press the tilde key (`~` / `` ` ``) on your keyboard.
  - Launches a 120-particle HTML5 Canvas confetti explosion and reveals the prank.
- **Zero Dependencies & Fully Responsive**: Handcrafted in vanilla HTML5, CSS3, and JavaScript. Optimized for both mobile phones and desktop browsers.

---

## 📂 Project Structure

```text
assignmentPrank/
├── index.html        # Main web app (viewer, styling, modals, audio, and prank logic)
├── assignment.pdf    # Source assignment PDF document
├── page-1.png        # High-resolution rendered preview page (150 DPI)
├── banglaQR.jpg      # The Bangla QR payment image
├── README.md         # Documentation
└── LICENSE           # MIT License
```

---

## 🚀 How to Run Locally

You don't need any build tools or package managers. Simply open `index.html` in any modern web browser:

```bash
# Option 1: Open directly
xdg-open index.html   # Linux
open index.html       # macOS
start index.html      # Windows

# Option 2: Serve via Python local server
python3 -m http.server 8000
# Then visit http://localhost:8000 in your browser
```

---

## 🌐 Free 1-Click Deployment

To share the prank with your friends, host it for free:

### 1. GitHub Pages (Recommended)
1. Push this repository to GitHub.
2. Go to **Settings** > **Pages**.
3. Under **Branch**, select `main` and `/ (root)`.
4. Click **Save**. Your site will be live at `https://<your-username>.github.io/assignmentPrank/`!

### 2. Vercel / Netlify / Cloudflare Pages
- Drag and drop the folder into [Netlify Drop](https://app.netlify.com/drop) or import the repository on [Vercel](https://vercel.com).

---

## 🛠️ Customization

### 1. Change the Assignment PDF & Cover Image
If you want to prank friends with a different course or assignment:
1. Replace `assignment.pdf` with your own PDF.
2. Render Page 1 to PNG at 150 DPI:
   ```bash
   pdftoppm -png -r 150 assignment.pdf page
   ```
   *(This outputs `page-1.png` matching the exact aspect ratio).*

### 2. Change the QR Code
Replace `banglaQR.jpg` with your own bKash, Nagad, or personal QR code image.

### 3. Change the Price or Currency
Search for `5,000` in `index.html` and change the amount or currency to whatever you want (e.g., `10,000 ৳` or `$50`).

### 4. Custom WhatsApp Contact & Message
In `index.html`, locate the `complainWhatsApp()` and `confirmBiryaniDeal()` functions to edit the prefilled WhatsApp text or change the username (currently set to `@oceanmallik` via `https://wa.me/oceanmallik?text=...`).

---

## ⚠️ Disclaimer

This project is created strictly for harmless fun, pranks, and entertainment between friends and university classmates. No actual unauthorized charges are processed. Always remind your friends to start their assignments on time! 😉

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
