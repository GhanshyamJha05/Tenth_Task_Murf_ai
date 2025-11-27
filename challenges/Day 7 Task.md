# Day 7 – Food & Grocery Ordering Voice Agent

## Overview
Build a shopping assistant for your favorite food ordering/quick commerce platform.

For the **primary goal**:
- Create a sample catalog in JSON format
- Bot understands what user wants (items, quantities, or "ingredients for X")
- Add items to cart, keep track of order as conversation progresses
- When user is done, final order is "placed" by saving to JSON file

For the **advanced goals**:
- Build mock order tracking system with status changes
- Agent can answer "where is my order?" by checking status
- Agent has access to previous orders, not just current one
- All persistence using JSON files or database

## Primary Goal (MVP) – Food & Grocery Ordering + Cart → Order JSON

**Objective:** Build a voice agent that lets a user order food and groceries from a catalog, intelligently adds items to a cart (including bundled ingredients), keeps track of the order, and saves the final order to a JSON file when the user is done.

### Tasks

1. **Create a catalog JSON file**
2. **Set up the ordering assistant persona**
3. **Implement cart management**
4. **Handle "ingredients for X" style requests intelligently**
5. **Place the order and save it to a JSON file**

### MVP Completion Checklist
- Created catalog JSON with variety of food and grocery items
- Agent can add specific items and quantities to cart
- Agent intelligently adds multiple items for "ingredients for X" requests
- Agent shows/lists cart when asked
- When user is done, agent confirms final order and writes to JSON file

## Advanced Goals

1. **Mock Order Tracking Over Time** - Orders transition through statuses
2. **Order History and Previous Orders** - Keep history of all orders
3. **Multiple Concurrent Orders** - Support multiple active orders
4. **Smart Reorder / Recommendations** - Use past orders for suggestions
5. **Budget or Constraints-Aware Ordering** - Filter by price/dietary tags

## Resources
- https://docs.livekit.io/agents/build/prompting/
- https://docs.livekit.io/agents/build/tools/
