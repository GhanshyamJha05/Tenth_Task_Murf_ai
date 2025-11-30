# Day 10: Voice Improv Battle 🎭

A voice-first improv game show where you perform hilarious scenarios and get real-time reactions from an AI host!

## 🌟 Features

### Voice Improv Game Show
- **Energetic AI Host**: Meet your witty, high-energy game show host who guides you through improv scenarios
- **Unique Scenarios**: 8 hilarious improv situations to perform (time travelers, escaped food, cursed objects, and more!)
- **Real-time Reactions**: Get honest, varied feedback - sometimes supportive, sometimes critical, always entertaining
- **3-Round Structure**: Complete game with intro, 3 performance rounds, and closing summary
- **Live Transcript**: View the full conversation in real-time with a beautiful sliding transcript panel
- **Message History**: See everything you said and what the agent responded with timestamps

### Game Flow
1. **Welcome**: Enter your stage name and join the show
2. **Introduction**: Host explains the rules and sets the energy
3. **Round 1-3**: 
   - Host presents a scenario
   - You improvise in character
   - Say "end scene" when done
   - Host reacts with honest feedback
4. **Closing**: Host summarizes your improv style and memorable moments

### Host Personality
- High-energy and entertaining
- Witty with great comedic timing
- Varied reactions (not always supportive!)
- Sometimes amused, sometimes unimpressed, sometimes pleasantly surprised
- Light teasing but always respectful

## 🛠️ Tech Stack

- **Frontend**: Next.js 15, React, TypeScript, Framer Motion
- **Backend**: Python, LiveKit Agents SDK
- **Voice**: Deepgram STT, Google Gemini 2.0 Flash, **Murf Falcon TTS**
- **Real-time**: LiveKit WebRTC

## 🎭 Sample Scenarios

1. "You are a time-travelling tour guide explaining modern smartphones to someone from the 1800s."
2. "You are a restaurant waiter who must calmly tell a customer that their order has escaped the kitchen."
3. "You are a customer trying to return an obviously cursed object to a very skeptical shop owner."
4. "You are a barista who has to tell a customer that their latte is actually a portal to another dimension."
5. "You are a tech support agent helping an alien understand how to use a toaster."
6. "You are a museum guide explaining why the dinosaur exhibit is currently doing yoga."
7. "You are a pizza delivery person who accidentally delivered to the wrong century."
8. "You are a librarian explaining to a dragon why they can't check out books without a library card."

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- Node.js 18+
- pnpm
- LiveKit Cloud account (or local server)
- API Keys: Deepgram, Google AI, Murf

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/GhanshyamJha05/Tenth_Task_murf_ai.git
cd Tenth_Task_murf_ai
```

2. **Backend Setup**
```bash
cd backend
python -m venv .venv
.venv\Scripts\activate  # Windows
source .venv/bin/activate  # Mac/Linux
pip install -r requirements.txt
cp .env.example .env.local
# Add your API keys to .env.local
```

3. **Frontend Setup**
```bash
cd frontend
pnpm install
cp .env.example .env.local
# Add your LiveKit credentials to .env.local
```

4. **Start LiveKit Server** (in project root)
```bash
.\livekit-server.exe --dev  # Windows
./livekit-server --dev      # Mac/Linux
```

5. **Start Backend Agent**
```bash
cd backend
.venv\Scripts\python.exe src/agent.py dev
```

6. **Start Frontend**
```bash
cd frontend
pnpm dev
```

7. **Open Browser**
Navigate to `http://localhost:3000`

## 🎮 How to Play

1. **Enter Your Name**: Type your stage name on the welcome screen
2. **Click "START IMPROV BATTLE!"**: Connect to the voice agent
3. **Listen to the Host**: They'll introduce the game and explain the rules
4. **Get Your Scenario**: Host will present your first improv scenario
5. **Perform**: Act out the scenario in character!
6. **End Scene**: Say "end scene" or "done" when you finish
7. **Get Feedback**: Host will react to your performance
8. **View Transcript**: Click the "Transcript" button (top-right) to see the full conversation
9. **Repeat**: Complete 3 rounds total
10. **Closing**: Host summarizes your improv style

## 💬 Tips for Great Improv

- **Commit to the character**: Fully embrace the role
- **Add details**: Specific details make it funnier
- **React emotionally**: Show feelings appropriate to the situation
- **Keep it moving**: Don't overthink, just go with it
- **Have fun**: The host appreciates creativity and boldness!

## 📝 Conversation Transcript Feature

The app includes a real-time conversation transcript that captures everything said during your improv session:

### Features:
- **Live Updates**: Messages appear as they're spoken
- **Speaker Labels**: Clear distinction between 🎭 HOST and 🎤 YOU
- **Timestamps**: Each message shows when it was said
- **Sliding Panel**: Beautiful animation from the right side
- **Auto-scroll**: Automatically scrolls to latest message
- **Session Storage**: Transcript persists during your session

### How to Use:
1. Click the **"Transcript"** button in the top-right corner
2. View the full conversation history
3. The badge shows the number of messages
4. Click the X or button again to close the panel

### UI Design:
- Agent messages: Purple bubbles on the left
- User messages: Pink bubbles on the right
- Dark theme matching the stage aesthetic
- Smooth animations and transitions

## 📁 Project Structure

```
├── backend/
│   ├── src/
│   │   ├── agent.py          # Improv host agent with game logic
│   │   └── murf_tts.py       # Murf TTS integration
│   └── .env.local            # Backend config
├── frontend/
│   ├── app/
│   │   ├── page.tsx          # Main improv game page
│   │   └── api/
│   │       └── connection-details/
│   │           └── route.ts  # LiveKit connection API
│   ├── components/
│   │   └── app/
│   │       ├── improv-welcome.tsx    # Welcome screen
│   │       └── improv-session.tsx    # Game session with transcript
│   └── .env.local            # Frontend config
└── livekit-server.exe        # LiveKit server
```

## 🔧 Configuration

### Backend (.env.local)
```env
LIVEKIT_URL=ws://localhost:7880
LIVEKIT_API_KEY=your_key
LIVEKIT_API_SECRET=your_secret
DEEPGRAM_API_KEY=your_key
GOOGLE_API_KEY=your_key
MURF_API_KEY=your_key
```

### Frontend (.env.local)
```env
NEXT_PUBLIC_LIVEKIT_URL=ws://localhost:7880
LIVEKIT_API_KEY=your_key
LIVEKIT_API_SECRET=your_secret
```

## 🎯 Key Features Implemented

✅ Single-player improv game show  
✅ AI host with varied personality  
✅ 8 unique improv scenarios  
✅ 3-round game structure  
✅ Real-time voice interaction  
✅ Honest, varied feedback (supportive, critical, amused)  
✅ Game state management  
✅ Beautiful stage-themed UI  
✅ Smooth animations and effects  
✅ Murf Falcon TTS for ultra-fast responses  
✅ **Live conversation transcript with sliding panel**  
✅ **Real-time message capture (agent + user)**  
✅ **Timestamped conversation history**  
✅ **Beautiful chat UI with speaker labels**  

## 🐛 Troubleshooting

### Agent not responding
- Check backend logs for errors
- Verify all API keys are set
- Ensure LiveKit server is running

### Can't connect
- Make sure all three servers are running (LiveKit, Backend, Frontend)
- Check that ports 7880 and 3000 are available
- Verify .env.local files are configured

### Host doesn't react
- Make sure to say "end scene" or "done" to signal you're finished
- Check that your microphone is working
- Look at backend logs for any errors

## 📝 License

MIT License - See LICENSE file for details

## 👨‍💻 Author

Ghanshyam Jha
- GitHub: [@GhanshyamJha05](https://github.com/GhanshyamJha05)

## 🙏 Acknowledgments

- LiveKit for the amazing real-time infrastructure
- Murf AI for ultra-fast Falcon TTS
- Google Gemini for intelligent, creative conversations
- Deepgram for accurate speech recognition

---

**Built for the 10 Days of Voice Agents Challenge - Day 10** 🎭🎉

**Powered by Murf Falcon TTS - The Fastest Voice AI!** ⚡
