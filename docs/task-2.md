# Task 2: Create a Real-time Assist Skill (8 minutes)

Real-time Assist listens to the call and suggests what the agent should say, using a knowledge base you provide.

## Step 1: Create the knowledge base

1. In Control Hub, click **Contact Centre > Customer experience > AI Agents**, then **Build your AI Agent**. **Webex AI Agent Studio** opens in a new tab. Allow pop-ups if asked.
2. In the left menu, click **Knowledge** (database icon), then **Create knowledge base**:
   - **Name:** `CiscoLive_KB`
   - **Description:** `Cisco Live Coffee Co. menu, hours and order policies`
3. Click **Create**, then click **Add an article**:
   - **Source name:** `Cisco Live FAQ`
   - **Description:** `Menu, hours and order policies` *(required; **Add source** stays grey without it)*
   - **Article body:** paste the FAQ below.
4. Click **Add source**. The status changes from **Queued for Processing** to ready in a minute or two. Carry on while it processes.

```
Cisco Live Coffee Co. - FAQ

HOURS AND LOCATION
- World of Solutions hall, next to the Cisco booth. Open daily 7:00 AM - 7:00 PM.

MENU
- Latte $4.50 / $5.00. Cappuccino $4.25 / $4.75. Cold brew $4.25 / $4.75.
- Flavours: vanilla, caramel, hazelnut (+$0.50). Plant milks (oat, almond, soy) +$0.60.

ALLERGENS
- Almond milk and hazelnut syrup contain tree nuts.
- Croissants and muffins contain gluten, egg and dairy.

ORDERS AND REFUNDS
- Every order has a 5-digit order number. Normal preparation time is 10 minutes.
- If an order is more than 15 minutes late, apologise and offer a free replacement drink or a full refund.
- Refunds go back to the original payment method in 3-5 business days.
- Always confirm the 5-digit order number before a refund or replacement.
```

## Step 2: Create and publish the skill

1. In the left menu, click **AI Assistant skills** (✨), then **Create skill > Start from scratch**.
2. Enter:
   - **Skill name:** `CiscoLive_Assist`
   - **Goal:** `Help Cisco Live agents answer questions about orders, menu, allergens and store hours, and resolve order issues politely.`
3. Click **Create**.
4. In **Instructions**, paste:
   ```
   Suggest short, friendly replies for the agent. Use the knowledge base for prices, allergens, hours and refund policy - never invent them. For late orders, confirm the order number and offer a replacement or refund. If the customer is upset, suggest an apology first.
   ```
5. Click **Save changes**.
6. Click the **Knowledge** tab and select **`CiscoLive_KB`**. Click **Save changes**.
7. Click **Publish**, enter the comment `v1`, and click **Publish**. The badge changes to **Published**.

---

[Continue to Task 3](task-3.md)

