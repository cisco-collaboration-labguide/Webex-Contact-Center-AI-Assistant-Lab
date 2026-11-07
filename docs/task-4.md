# Task 4: Stream Call Audio to the AI (5 minutes)

Transcripts, Real-time Assist, sentiment, and summaries all need the call audio. Add **Start Media Stream** to the flow's **AgentAnswered** event, so audio is forked as soon as the agent answers.

> **Important:** put Start Media Stream in the **Event flows** canvas, not in the main flow before Queue Contact. In the main flow it fails, and the agent sees *"Live transcription isn't available for this call."*

## Step 1: Add the activity

1. Go to **Customer experience > Flows**. On **Cisco_Live**, click **Go to Flow Designer**.
2. Turn **Edit** to **On**.
3. Click the **Event flows** tab. Find **AgentAnswered**, which currently goes to **ScreenPop_sd8**.
4. Click the link **AgentAnswered → ScreenPop_sd8**, then click **✕ Delete link**.
5. In the **Activities** library, search for `Start Media`. Drag **Start Media Stream** next to **AgentAnswered**.
6. Click the new activity, click the **pencil** by **Activity label**, rename it `MediaStreamAI`, and click **✓**. Nothing else needs configuring.
7. Draw three links:

   | From | Port | To |
   |---|---|---|
   | AgentAnswered | out | MediaStreamAI |
   | MediaStreamAI | out | ScreenPop_sd8 |
   | MediaStreamAI | Failure | ScreenPop_sd8 |

   > Sending **Failure** onward means that if streaming fails, the call still continues normally.

## Step 2: Validate and publish with the Live label

1. Turn on **Validation** and confirm **Ready to publish**.
2. Click **Publish Flow**.
3. In **Select version labels**, add **Live**. *Latest* is applied automatically.

   > The **Cisco Live** channel uses the **Live** label. If you skip this, calls keep running the old version.

4. Enter a comment, such as `AI media stream`, and click **Publish Flow**.

---

[Continue to Task 5](task-5.md)

