# Task 1: Turn On the AI Features (5 minutes)

All AI features start **off** in this tenant. You turn them on for the organization, then confirm the **Cisco Live** queue picks them up.

## Step 1: Enable the global AI features

1. Sign in to `https://admin.webex.com` as `cholland@cb472.dc-01.com`.
2. In the left menu, click **Contact Centre**.
3. Under **Desktop experience**, click **AI features** (✨). Stay on the **Global** tab.
4. Turn on each item below. **Apply to all queues** switches on automatically. Leave it on.

   | Section | Turn on |
   |---|---|
   | **Auto CSAT** | Auto CSAT |
   | **Generated summaries** | Generated summaries, then tick ☑ **Mid-call summaries**, ☑ **Call drop summaries**, and ☑ **Wrap-up summaries with auto-suggested wrap-up reason** |
   | **Real-time transcriptions** | Real-time transcriptions |
   | **Sentiment analysis** | Sentiment analysis |
   | **Real-time assistance** | Real-time assistance |

   Leave **AI routing** and **Agent Wellbeing** off. They aren't part of this lab.

5. Click **Save** (bottom right) and wait for **"updated successfully"**.

## Step 2: Check the queue

1. Click the **Queue** tab, then click **Cisco Live**.
2. Confirm that **Auto CSAT**, **Generated summaries**, **Real-time transcriptions**, and **Sentiment analysis** show **Global settings applied**, with their switches on.
   - If any **Apply …** switch is off, turn it on and click **Save**.
3. Leave **Real-time assistance** for now. It needs a skill, which you create in Task 2.

> **Note:** Summary types are managed only at the global level. Every queue inherits them.

---

[Continue to Task 2](task-2.md)

