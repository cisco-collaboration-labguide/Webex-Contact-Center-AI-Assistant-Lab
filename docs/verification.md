# Verification Checklist

| ✓ | Item |
|---|---|
| ☐ | Global AI features on: Auto CSAT, Generated summaries (mid-call, call drop, wrap-up), Real-time transcriptions, Sentiment, Real-time assistance |
| ☐ | Queue **Cisco Live** inherits the features, and Real-time assistance uses `CiscoLive_Assist` |
| ☐ | `CiscoLive_KB` has the FAQ article; `CiscoLive_Assist` is **Published** |
| ☐ | Wrap-up codes **Order Status**, **Order Issue - Refund**, and **Menu and Allergens** exist |
| ☐ | Flow **Cisco_Live** published with label **Live**: AgentAnswered → MediaStreamAI → ScreenPop |
| ☐ | Live transcript, AI suggestion, mid-call summary, and wrap-up summary with suggested code all seen |
| ☐ | Call drop summary seen on callback |

## Troubleshooting

| Symptom | Fix |
|---|---|
| *"Live transcription isn't available for this call"* | Start Media Stream must be on the **AgentAnswered** event in **Event flows**. Check the flow was published with the **Live** label. In Flow Designer **Debug**, confirm `MediaStreamAI` shows **Success** |
| No AI suggestions | Check the queue has Real-time assistance on with `CiscoLive_Assist`, the skill is **Published**, and the knowledge source has finished processing |
| Skill not listed in **Select a skill** | Publish the skill, then reload Control Hub |
| **Add source** greyed out | Fill in the article **Description** |
| No AI-suggested wrap-up code | Check that **Wrap-up summaries with auto-suggested wrap-up reason** is ticked. Have a real conversation of 20+ seconds |
| Agent never rings | Check the agent is **Available** on team **CiscoLive2** |
| Duplicate-label validation error | Rename the activity to a unique label, for example `MediaStreamAI2` |
