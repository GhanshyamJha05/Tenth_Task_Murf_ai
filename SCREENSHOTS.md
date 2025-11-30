# 📸 Voice Improv Battle - Screenshots & Features

## 🎭 Welcome Screen
The game starts with an energetic welcome screen where players enter their stage name.

**Features:**
- Animated spotlight effects
- Stage curtain design
- Player name input
- "START IMPROV BATTLE!" button

---

## 🎤 Game Session View
The main game interface with real-time voice interaction.

**Features:**
- **Player Info Card** (top-left): Shows contestant name
- **Transcript Button** (top-right): Opens conversation history
- **Central Microphone**: Visual indicator of speaking state
  - 🎭 Pink when HOST is speaking
  - 🎤 Cyan when YOU are speaking
  - Gray when idle
- **Status Display**: Shows current state
  - "🎭 HOST IS SPEAKING" - Listen to the host
  - "🎤 YOUR TURN!" - Perform your improv
  - "⏸️ READY" - Waiting for next cue
  - "🔌 CONNECTING..." - Establishing connection
- **How to Play Instructions**: Quick reference guide
- **END SHOW Button**: Disconnect from the session

---

## 💬 Live Transcript Panel
Real-time conversation history with beautiful UI.

**Features:**
- **Sliding Animation**: Smooth slide-in from right
- **Message Bubbles**:
  - 🎭 HOST messages: Purple bubbles on left
  - 🎤 PLAYER messages: Pink bubbles on right
- **Timestamps**: Each message shows time sent
- **Speaker Labels**: Clear identification of who said what
- **Auto-scroll**: Automatically scrolls to latest message
- **Message Counter**: Badge shows total messages
- **Close Button**: X button to hide panel

**Transcript UI Details:**
```
┌─────────────────────────────────────┐
│ Conversation                    [X] │
│ Full transcript of your session     │
├─────────────────────────────────────┤
│                                     │
│  ┌──────────────────────────┐      │
│  │ 🎭 HOST        10:30 AM  │      │
│  │ Welcome to Improv Battle!│      │
│  └──────────────────────────┘      │
│                                     │
│      ┌──────────────────────────┐  │
│      │ 🎤 PLAYER     10:30 AM  │  │
│      │ Hi! I'm ready to play!  │  │
│      └──────────────────────────┘  │
│                                     │
├─────────────────────────────────────┤
│ 💾 Transcript is saved for this    │
│    session only                     │
└─────────────────────────────────────┘
```

---

## 🎬 Game Flow Visualization

```
┌─────────────────────────────────────────────────────────┐
│                    WELCOME SCREEN                       │
│                  Enter Your Name                        │
│              [START IMPROV BATTLE!]                     │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                   INTRO PHASE                           │
│   Host: "Welcome! Here's how the game works..."        │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                   ROUND 1                               │
│   Host: "Your scenario: [scenario]. Action!"           │
│   Player: [Performs improv]                            │
│   Player: "End scene!"                                 │
│   Host: [Gives honest feedback]                        │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                   ROUND 2                               │
│   [Same structure as Round 1]                          │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                   ROUND 3                               │
│   [Same structure as Round 1]                          │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                   CLOSING                               │
│   Host: "You're a [style] improviser! Thanks!"        │
└─────────────────────────────────────────────────────────┘
```

---

## 🎨 Visual Design Elements

### Color Scheme
- **Background**: Black with radial gradient
- **Primary**: Purple (#A855F7)
- **Secondary**: Pink (#EC4899)
- **Accent**: Yellow (#FACC15)
- **Cyan**: (#06B6D4) for listening state

### Animations
- **Spotlight Effects**: Pulsing yellow and pink blurs
- **Microphone**: Scales up/down based on speaking state
- **Transcript Panel**: Smooth slide-in/out animation
- **Messages**: Fade-in animation for new messages
- **Buttons**: Hover scale and color transitions

### Typography
- **Headers**: Bold, gradient text
- **Body**: Clean, readable sans-serif
- **Status**: Large, attention-grabbing
- **Transcript**: Small, compact for readability

---

## 🔊 Audio States

| State | Visual Indicator | Description |
|-------|-----------------|-------------|
| **Connecting** | Gray mic, "CONNECTING..." | Establishing connection to LiveKit |
| **Ready** | Gray mic, "READY" | Connected, waiting for interaction |
| **Agent Speaking** | Pink mic, pulsing | Host is talking, listen carefully |
| **User Speaking** | Cyan mic, pulsing | Your turn to perform improv |
| **Processing** | Gray mic, "READY" | Agent is thinking/processing |

---

## 📱 Responsive Design

The interface adapts to different screen sizes:

- **Desktop**: Full-width transcript panel (500px)
- **Mobile**: Full-screen transcript overlay
- **Tablet**: Optimized spacing and sizing

---

## ⚡ Performance Features

- **Real-time Updates**: Instant message display
- **Smooth Animations**: 60fps animations using Framer Motion
- **Efficient Rendering**: React optimization for transcript
- **Auto-cleanup**: Transcript clears on disconnect
- **Duplicate Prevention**: Smart message deduplication

---

## 🎯 User Experience Highlights

1. **Clear Visual Feedback**: Always know who's speaking
2. **Easy Navigation**: Simple, intuitive controls
3. **Conversation History**: Never lose track of what was said
4. **Beautiful Aesthetics**: Stage-themed design immerses you in the show
5. **Accessibility**: High contrast, clear labels, readable text

---

**Built with ❤️ for the 10 Days of Voice Agents Challenge**
**Powered by Murf Falcon TTS ⚡**
