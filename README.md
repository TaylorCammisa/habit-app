# Habit App

A mobile app for building better habits. Create habits, check them off each day,
look back at your history, and get reminders at the times that work for you.
All data stays on your device.

> 🚧 **Status:** In early development, built step by step as a learning project.

## Planned Features

- Create, edit, and delete habits
- Daily check-off for each habit
- History log of past days
- Optional notes on a habit for a specific day
- Local reminders (Morning, Afternoon, and/or Night)

## Tech Stack

- [Expo](https://expo.dev) SDK 58
- React Native
- TypeScript
- Expo Router (file-based navigation)

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org) 22 or newer
- [Git](https://git-scm.com)
- A free [Expo account](https://expo.dev/signup)
- The **Expo Go** app on your phone ([iOS](https://apps.apple.com/app/expo-go/id982107779) / [Android](https://play.google.com/store/apps/details?id=host.exp.exponent)), signed in to your Expo account

### Running the App

1. Clone the repository:
   ```
   git clone https://github.com/TaylorCammisa/habit-app.git
   ```
2. Move into the project folder:
   ```
   cd habit-app
   ```
3. Install dependencies:
   ```
   npm install
   ```
4. Log in to Expo (use the same account as in Expo Go):
   ```
   npx expo login
   ```
5. Start the development server:
   ```
   npx expo start
   ```
6. Open Expo Go on your phone and tap **habit-app** under **Development Servers**.

> **Tip:** Your phone and computer must be on the same Wi-Fi network.
> If the app doesn't appear in Expo Go, scan the QR code shown in the terminal:
> on **Android**, use the scanner in Expo Go; on **iPhone**, use the Camera app.

## Project Structure

```
src/
├── app/          # Screens and navigation (Expo Router: every file is a route)
├── components/   # Reusable UI components (buttons, cards, habit rows)
├── theme/        # Design tokens: colors, typography, spacing
├── hooks/        # Custom React hooks that connect the UI to data
├── data/         # Storage layer: the only code that reads or writes saved data
├── utils/        # Pure logic with no UI (date helpers, streak calculations)
└── types/        # Shared TypeScript types
```

Folders are created as they're needed, so not all of them exist yet.

**Dependency rule:** code only imports from layers below it. Screens can use
components and hooks; hooks can use `data/` and `utils/`; `data/` and `utils/`
never import UI code. This keeps the business logic easy to test and the
storage layer easy to change.