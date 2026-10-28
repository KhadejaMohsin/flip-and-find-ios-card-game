# flip-and-find-ios-card-game


<p align="center">
  <img src="screenshots/app-icon.png" width="120" alt="Flip & Find app icon">
</p>

<h1 align="center">Flip & Find</h1>

<p align="center">
  <b>Match fast. Think faster.</b><br>
  A race-the-clock memory card game for iPhone, built with SwiftUI.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Swift-6-F05138?logo=swift&logoColor=white" alt="Swift 6">
  <img src="https://img.shields.io/badge/SwiftUI-iOS%2026-0A84FF?logo=apple&logoColor=white" alt="SwiftUI iOS 26">
  <img src="https://img.shields.io/badge/Xcode-26-147EFB?logo=xcode&logoColor=white" alt="Xcode 26">
</p>

---

## About

**Flip & Find** takes the classic memory match game and adds pressure. Flip two cards at a time to find matching pairs, but you only have a limited number of **moves** *and* a ticking **timer**. If either one runs out, you get booed off the table. Match every pair in time and confetti rains down.

Built by **Khadeja Mohsin** for COSC 3326 Mobile Programming (Fall 2026) at St. Edward's University.

## Screenshots

| Home | Gameplay | Medium Mode |
|:---:|:---:|:---:|
| <img src="screenshots/home.png" width="220"> | <img src="screenshots/gameplay.png" width="220"> | <img src="screenshots/medium-mode.png" width="220"> |
| **How to Play** | **Settings** | **High Scores** |
| <img src="screenshots/rules.png" width="220"> | <img src="screenshots/settings.png" width="220"> | <img src="screenshots/high-scores.png" width="220"> |

## Features

- **Two ways to lose.** You're racing both a move limit and a countdown timer.
- **Live scoring.** Every move shows the points it earned, including streak bonuses for back-to-back matches.
- **Three difficulty levels.** Easy, Medium, and Hard change the card count, move limit, timer, and point multiplier.
- **Saved high scores.** A top-10 leaderboard persists between launches, ranked with medals and filterable by difficulty.
- **Win and lose screens.** A custom confetti particle animation when you win; "Boo! Better luck next time" with falling 👎🍅😢 when you lose.
- **Peek mode.** All the cards are shown briefly before the game starts.
- **Pause and Reset.** Pausing hides the cards (no cheating), and the game auto-pauses when the app goes to the background. Reset deals a fresh shuffle with the score set back to 0.
- **Polish.** 3D card-flip animations, haptic feedback, and a card-table green theme.

## How to Play

1. Tap a card, then tap a second card.
2. If they match, they stay face up. If not, they flip back over.
3. Find every pair before your moves or time run out.

### Scoring

| Action | Points |
|---|---|
| Match | **+100** |
| Streak bonus (each match in a row) | **+25** extra per streak level |
| Miss | **−10** |
| Time left at the end | **+5** per second |
| Moves left at the end | **+10** per move |

All points are multiplied by the difficulty level: **×1** Easy, **×2** Medium, **×3** Hard.

### Difficulty

| Level | Cards | Moves | Time |
|---|:---:|:---:|:---:|
| Easy | 12 | 20 | 90 s |
| Medium | 16 | 26 | 80 s |
| Hard | 20 | 32 | 75 s |

## Built With

- **Swift 6** and **SwiftUI**
- `@Observable` game model holding all the rules: matching, scoring, timer, win/lose
- `TimelineView` + `Canvas` for the confetti and "boo" particle effects
- `Codable` + `UserDefaults` for saved high scores
- `@AppStorage` for persistent settings
- `UIImpactFeedbackGenerator` / `UINotificationFeedbackGenerator` for haptics

## Project Structure

```
FlipAndFind/
├── FlipAndFindApp.swift        # App entry point and credits splash
├── ContentView.swift           # Home screen
├── GameView.swift              # Game screen, score bar, card grid, pause
├── GameModel.swift             # Game rules: matching, scoring, timer, win/lose
├── Models.swift                # Card, Difficulty, and game state types
├── HighScoreStore.swift        # Saving and loading high scores
├── ResultViews.swift           # Win and lose panels
├── FallingParticlesView.swift  # Confetti / boo animation
├── CardView.swift              # Card front/back and flip animation
├── SettingsView.swift          # Difficulty and gameplay options
├── HighScoresView.swift        # Leaderboard
├── RulesView.swift             # How to play
├── SplashView.swift            # Credits screen
├── Theme.swift                 # Colors and button styles
├── Haptics.swift               # Vibration feedback
└── Assets.xcassets             # App icon, launch art, card images
```

## Getting Started

**Requirements:** a Mac with Xcode 26 or later. The deployment target is iOS 26.5.

```bash
git clone https://github.com/<your-username>/flip-and-find-ios.git
cd flip-and-find-ios
open FlipAndFind.xcodeproj
```

Then pick an iPhone simulator (for example, iPhone 17 Pro) and press **⌘R** to run.

> Haptic feedback only works on a physical iPhone; the simulator doesn't vibrate.

## Credits

- Design and development: **Khadeja Mohsin**
- Playing card images were provided as course materials for COSC 3326.

---

<p align="center">© 2026 Khadeja Mohsin</p>
