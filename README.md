# 🛒 Day 7: Voice-Powered Grocery Ordering Agent

A conversational AI shopping assistant built with LiveKit Agents and Murf AI TTS that lets you order groceries naturally using just your voice - with real-time cart visualization!

## 🎯 Features

### Smart Shopping Capabilities
- **80+ Products** - Comprehensive catalog across 8 categories
- **35+ Recipe Intelligence** - Say "I want to make pasta" and get all ingredients automatically
- **Natural Conversation** - No rigid commands, just talk naturally
- **Multi-Item Parsing** - "Milk, eggs, and bread" → 3 separate items with individual prices
- **Real-Time Cart** - Beautiful animated cart that updates as you speak
- **Smart Price Lookup** - Automatic price matching from catalog

### Categories & Items
**Groceries:** Bread, Flour, Sugar, Salt, Atta, Besan
**Dairy & Eggs:** Milk, Eggs, Butter, Cheese, Yogurt, Paneer, Cream
**Condiments:** Ketchup, Mayo, Soy Sauce, Honey, Olive Oil, Ghee, Pickle
**Pasta & Grains:** Spaghetti, Rice, Noodles, Oats, Poha, Dal, Chickpeas
**Snacks:** Chips, Cookies, Biscuits, Namkeen, Popcorn, Nuts
**Beverages:** Juice, Coffee, Tea, Water, Soft Drinks, Lassi
**Prepared Foods:** Pizza, Sandwiches, Samosa, Spring Rolls
**Fruits & Vegetables:** 20+ fresh produce items

### Recipe Intelligence (35+ Recipes)
**Indian:** Dal, Roti, Paratha, Biryani, Pulao, Aloo Gobi, Paneer Curry, Chole, Rajma, Sambar, Raita, Poha
**International:** Pasta, Spaghetti, Pizza, Salad, Omelet, Pancakes, Soup, Smoothie
**Beverages:** Tea, Coffee, Lassi, Juice

### Voice Integration
- **Murf AI Falcon TTS** - Ultra-fast, natural voice (Ryan voice, 1.15x speed)
- **Deepgram STT** - Accurate real-time speech recognition
- **Google Gemini 2.5 Flash** - Intelligent conversation with function calling

### UI Features
- **Animated Welcome Screen** - Engaging entry point with floating icons
- **Real-Time Cart Display** - Updates instantly as items are added
- **Individual Item Cards** - Each item shows name, quantity, and price
- **Live Total Calculation** - Running total updates automatically
- **Order Success Animation** - Celebration screen with order ID and delivery estimate
- **Smooth Transitions** - Framer Motion animations throughout

## 🚀 Quick Start

### Prerequisites
- Python 3.11+
- Node.js 18+
- pnpm (or npm)
- Murf AI API Key
- Deepgram API Key
- Google Gemini API Key

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/GhanshyamJha05/Seventh_task_murf_ai.git
cd Seventh_task_murf_ai/ten-days-of-voice-agents-2025
```

2. **Setup Backend**
```bash
cd backend
python -m venv .venv
.venv\Scripts\activate  # Windows
# or
source .venv/bin/activate  # Mac/Linux

pip install -r requirements.txt
```

3. **Configure Backend Environment**
Create `backend/.env.local`:
```env
LIVEKIT_URL=ws://localhost:7880
LIVEKIT_API_KEY=devkey
LIVEKIT_API_SECRET=secret
DEEPGRAM_API_KEY=your_deepgram_key
GOOGLE_API_KEY=your_gemini_key
MURF_API_KEY=your_murf_key
```

4. **Setup Frontend**
```bash
cd ../frontend
pnpm install
# or npm install
```

5. **Configure Frontend Environment**
Create `frontend/.env.local`:
```env
LIVEKIT_URL=ws://localhost:7880
LIVEKIT_API_KEY=devkey
LIVEKIT_API_SECRET=secret
NEXT_PUBLIC_LIVEKIT_URL=ws://localhost:7880
```

### Running the Application

1. **Start LiveKit Server** (Terminal 1)
```bash
cd ten-days-of-voice-agents-2025
./livekit-server.exe --dev  # Windows
# or
./livekit-server --dev  # Mac/Linux
```

2. **Start Grocery Agent** (Terminal 2)
```bash
cd backend
.venv\Scripts\activate  # Windows
python src/agent.py dev
```

3. **Start Frontend** (Terminal 3)
```bash
cd frontend
pnpm dev
# or npm run dev
```

4. **Open Browser**
Navigate to `http://localhost:3000`

## 💬 Example Conversations

### Simple Shopping
```
You: "I need milk and eggs"
Agent: "I've added 1 litre of milk and 1 dozen eggs to your cart"
Cart Shows: Milk (₹60) + Eggs (₹90) = ₹150
```

### Recipe Request
```
You: "I want to make pasta"
Agent: "For pasta, I'm adding spaghetti, tomato sauce, olive oil, and garlic"
Cart Shows: 4 items with individual prices
```

### Multi-Item Order
```
You: "Add milk, eggs, and bread"
Agent: "Added all three items to your cart"
Cart Shows: 3 separate items with correct prices
```

### Cart Management
```
You: "Make that 2 litres of milk"
Agent: "Updated milk quantity to 2"
Cart Updates: Milk quantity and total price
```

### Checkout
```
You: "Place my order"
Agent: "Order placed! Order ID: abc123. Total: ₹650. Delivery in 30-45 minutes"
Success Screen: Animated checkmark with order details
```

## 📁 Project Structure

```
.
├── backend/
│   ├── src/
│   │   ├── agent.py          # Main grocery ordering agent
│   │   └── murf_tts.py       # Murf AI TTS integration
│   ├── .env.local            # Backend environment variables
│   └── pyproject.toml        # Python dependencies
├── frontend/
│   ├── app/                  # Next.js app directory
│   ├── components/
│   │   └── app/
│   │       ├── cart-display.tsx      # Real-time cart visualization
│   │       ├── welcome-view.tsx      # Animated welcome screen
│   │       └── session-view.tsx      # Main session UI
│   ├── .env.local           # Frontend environment variables
│   └── package.json         # Node dependencies
├── shared-data/
│   ├── catalog.json          # 80 items with prices
│   └── orders/               # Order storage directory
│       ├── order_*.json      # Individual orders
│       └── order_history.json # Complete order history
├── challenges/
│   └── Day 7 Task.md         # Challenge documentation
└── livekit-server.exe        # LiveKit server binary
```

## 🔧 Customization

### Add More Items to Catalog

Edit `shared-data/catalog.json`:
```json
{
  "id": "NEW001",
  "name": "Your Item",
  "category": "Category",
  "price": 99,
  "unit": "unit",
  "brand": "Brand Name",
  "tags": ["vegetarian", "organic"]
}
```

### Add New Recipes

In `catalog.json`, add to the `recipes` section:
```json
"recipes": {
  "your recipe": ["ITEM_ID1", "ITEM_ID2", "ITEM_ID3"]
}
```

### Modify Voice Settings

In `backend/src/agent.py`:
```python
tts=murf_tts.TTS(
    voice="en-US-ryan",  # Change voice
    style="Conversational",  # Change style
)
```

In `backend/src/murf_tts.py`:
```python
"speed": 1.15,  # Adjust speech speed (1.0 = normal)
```

### Update Cart Prices

Edit the `CATALOG_PRICES` mapping in `frontend/components/app/cart-display.tsx` to match your catalog.

## 📊 Viewing Orders

### Check Individual Orders
```bash
# Windows
type shared-data\orders\order_*.json

# Mac/Linux
cat shared-data/orders/order_*.json
```

### View Order History
```bash
# Windows
type shared-data\orders\order_history.json

# Mac/Linux
cat shared-data/orders/order_history.json
```

### Order Format
```json
{
  "order_id": "abc123",
  "customer_name": "Guest",
  "timestamp": "2025-11-27T22:30:00",
  "status": "received",
  "items": [
    {
      "id": "DA001",
      "name": "Milk",
      "price": 60,
      "unit": "litre",
      "quantity": 1
    }
  ],
  "total": 60,
  "delivery_address": "123 Main St (Demo)"
}
```

## 🛠️ Tech Stack

- **Backend**: Python 3.11, LiveKit Agents SDK
- **Frontend**: Next.js 15, React, TypeScript, Framer Motion
- **Voice**: Murf AI Falcon TTS (fastest TTS API), Deepgram STT
- **LLM**: Google Gemini 2.5 Flash with function calling
- **Real-time**: LiveKit WebRTC
- **Storage**: JSON file system
- **UI**: Tailwind CSS, Custom animations

## 🎮 Testing Tips

### Test Basic Shopping
1. "I need milk"
2. "Add eggs"
3. "Show me my cart"
4. "Place my order"

### Test Recipe Intelligence
- "I want to make dal"
- "Get me ingredients for biryani"
- "I need items for breakfast"

### Test Multi-Item
- "Add milk, eggs, and bread"
- "I need potatoes, onions, and tomatoes"

### Test Cart Operations
- "Make that 2 kg"
- "Remove the butter"
- "Update milk to 3 litres"

## 📝 API Keys Required

1. **Murf AI** - Get from [murf.ai](https://murf.ai)
2. **Deepgram** - Get from [deepgram.com](https://deepgram.com)
3. **Google Gemini** - Get from [ai.google.dev](https://ai.google.dev)

## 🎓 Learning Resources

- [LiveKit Agents Documentation](https://docs.livekit.io/agents/)
- [Murf AI API Docs](https://murf.ai/api-docs)
- [Deepgram API Docs](https://developers.deepgram.com/)
- [Google Gemini API Docs](https://ai.google.dev/docs)
- [Framer Motion Docs](https://www.framer.com/motion/)

## 🤝 Contributing

This is a challenge project, but feel free to fork and customize for your own use cases!

## 📄 License

MIT License - See LICENSE file for details

## 🙏 Acknowledgments

Built as part of the Murf AI Voice Agent Challenge - Day 7
- Challenge by Murf AI
- LiveKit for the agents framework
- Inspired by modern quick commerce platforms like Blinkit, Zepto, Swiggy Instamart

## 🌟 Key Highlights

- **80 products** across 8 categories
- **35+ recipes** with automatic ingredient addition
- **Real-time cart** with smooth animations
- **Multi-item parsing** for natural shopping
- **Order history** with JSON persistence
- **Sub-second response** times with Murf Falcon
- **Beautiful UI** with Framer Motion animations

---

**Made with ❤️ by Ghanshyam Jha**

**🛒 Happy Voice Shopping!**
