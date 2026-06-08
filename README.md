🦊 Code Dojo
A tap-only block-coding game that teaches real programming concepts — no typing, no setup, one HTML file.
You guide a fox 🦊 to a gate ⛩️ by snapping together colour-coded blocks. Each lesson earns a belt, and every idea behind the blocks (sequences, loops, variables, decisions, events, memory, shortest-path search) is a concept that carries straight over to actual coding.
It was built for a bright, dyslexic kid, so the whole thing is designed to keep reading load low: clear fonts, cream background, big tap targets, colour cues, optional read-aloud, and short text. It works just as well for anyone learning the basics.
Play it
Open index.html in any modern browser, or visit the GitHub Pages link for this repo. Nothing to install.
Lessons
BeltLessonThe concept you actually learn🟨 YellowMovesSequence, loop, if/else🟧 OrangeEnergyVariables (a value the program tracks)🟩 GreenDecisionsConditions the program checks while it runs🟦 BlueControlsEvents and event handlers🟣 PurpleMemoryState — remembering the past to decide now🟤 BrownBest WayShortest path / breadth-first search🥋 BlackGradingCombine everything to solve fresh problems
Each lesson has a 📖 Learn side (worked examples with a "👀 Show me" demo) and a 🎓 Belt Test side (prove it yourself). Earn all six colour belts to unlock the Black Belt.
Lesson audio (optional)
Each learn lesson shows an audio bar with a play/pause button and a progress bar. It looks for one MP3 per lesson in a dojo-audio/ folder next to index.html:
your-repo/
├── index.html
└── dojo-audio/
    ├── l1.mp3   (Yellow – Moves)
    ├── l2.mp3   (Orange – Energy)
    ├── l3.mp3   (Green – Decisions)
    ├── l4.mp3   (Blue – Controls)
    ├── l5.mp3   (Purple – Memory)
    └── l6.mp3   (Brown – Best Way)

Add the files you have; the others simply show a greyed-out bar reading 🎧 add lN.mp3.
The player only goes live once the matching file loads, and playback is started by the user — so browsers never block it.
Record one warm, consistent voice. Scripts for all six are in code-dojo-audio-scripts.md.


Note: the audio is fetched at a relative path, so it plays from a real URL (GitHub Pages) or a local web server — not from a file opened directly off disk or inside an embedded preview.

Deploy on GitHub Pages

Put index.html (and the optional dojo-audio/ folder) in the repo root.
Settings → Pages → Build and deployment → Deploy from a branch.
Branch: main, folder: / (root). Save.
Wait a minute, then open the URL it gives you.

GitHub Pages serves index.html as the homepage automatically.
Progress and certificates

Progress (belts, stars, player name, dates) is saved in the browser's local storage. It's per device and per browser — switching computers starts fresh. A Reset button in the footer clears it.
Every earned belt can print a certificate (name, belt, date, seal) — tap the belt chip or the 🏅 button. Use the browser's Print dialog to save it as a PDF.

Under the hood

One self-contained index.html — HTML, CSS, and JavaScript, no build step, no frameworks, no dependencies to install.
No accounts, no tracking, no network calls except loading the typefaces from Google Fonts (it still works without them).
The board renders to a <canvas>; everything else is plain DOM.

Make it your own
Lessons are defined as data near the top of the script (grids, target moves, the blocks each level offers), so new levels or tweaks don't need engine changes. Grid legend: S start, G gate, * gem, # wall, B battery, C charger.
