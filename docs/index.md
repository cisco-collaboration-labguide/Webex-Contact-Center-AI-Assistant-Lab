# Webex Contact Center: AI Assistant for Agents Lab

**Estimated time:** 30 minutes
**Lab tenant:** `Atlas_Test_wxcc-test cb472.dc-01.com`

## Learning Objectives

Upon completion of this lab, you will be able to:

- Turn on the Cisco AI Assistant features for Webex Contact Center in Control Hub.
- Enable **real-time transcripts** for voice calls by adding one activity to an existing flow.
- Give agents **AI-powered Real-time Assist** backed by a simple knowledge base.
- Use AI-generated **mid-call** and **post-call summaries** with **suggested wrap-up codes**.
- Explain how **call drop summaries**, **sentiment**, and **Auto CSAT** add insight to every interaction.

## Scenario

The **Cisco Live** contact center is already running: callers dial in, hear a welcome message, and are queued to an agent on team **CiscoLive2**. Agents take each call "cold", type their own wrap-up notes, and pick a wrap-up code by hand.

In this lab you add the Cisco AI Assistant on top of that existing setup, without rebuilding anything:

| Business need | AI feature |
|---|---|
| See what the caller is saying, live | **Real-time transcripts** |
| Help newer agents give the right answer | **Real-time Assist** (AI suggestions from a knowledge base) |
| Quick context during a call, or for a supervisor or consult | **Mid-call summary** |
| Less after-call work and consistent coding | **Post-call summary with suggested wrap-up code** |
| Context when a caller gets cut off and calls back | **Call drop summary** |
| Satisfaction insight on every call, without surveys | **Auto CSAT** and **Sentiment analysis** |

**Pre-configured objects (use these, don't create new ones):**

| Object | Name | Notes |
|---|---|---|
| Channel | **Cisco Live** | Inbound telephony, number **+1 502 237 7363**, version label **Live** |
| Queue | **Cisco Live** | Longest available agent, team-based |
| Team | **CiscoLive2** | Agents: Anita Perez, Kellie Melby (Site-1) |
| Flow | **Cisco_Live** | WelcomePrompt → Queue Contact → hold music |

> The flow is listed in Control Hub as **`Cisco_Live`**. It is the flow used by the Cisco Live channel.

**Lab access**

| Item | Value |
|---|---|
| Control Hub | `https://admin.webex.com`, sign in as `cholland@cb472.dc-01.com` |
| Agent Desktop | `https://desktop.wxcc-us1.cisco.com`, sign in as `aperez@cb472.dc-01.com` (Anita Perez) |
| Passwords | Provided by the instructor |
| Test number | **+1 502 237 7363** |

You need a laptop with Chrome or Edge, a headset, and a mobile phone. Use a **separate browser profile or incognito window** for Agent Desktop, so the admin and agent sessions don't mix.

## Network Diagram

```
 Caller (mobile) ──► +1 502 237 7363 ──► Channel "Cisco Live" (label: Live)
                                              │
                                              ▼
 ┌─────────────────────────────────────────────────────────────────────┐
 │ Flow "Cisco_Live"                                                   │
 │  Main flow : NewPhoneContact ► WelcomePrompt ► QueueContact ► Music │
 │  Event flow: AgentAnswered ► MediaStreamAI ► ScreenPop ► End Flow   │
 │                              (Start Media Stream - added in lab)    │
 └───────────────┬───────────────────────────────────┬─────────────────┘
                 │ audio forked when agent answers    │ call
                 ▼                                    ▼
 ┌────────────────────────────────────┐   ┌──────────────────────────────┐
 │ Cisco AI Assistant (cloud)         │   │ Queue "Cisco Live"           │
 │  • Real-time transcription         │   │  AI: summaries, transcripts, │
 │  • Sentiment / Auto CSAT           │   │      sentiment, Auto CSAT,   │
 │  • Mid-call, wrap-up, call-drop    │   │      Real-time Assist skill  │
 │    summaries + suggested wrap code │   └──────────────┬───────────────┘
 │  • Real-time Assist ◄─ AI Agent    │                  ▼
 │    Studio skill + knowledge base   │   ┌──────────────────────────────┐
 └─────────────────┬──────────────────┘   │ Team "CiscoLive2"            │
                   └── AI Assistant ─────►│ Agent Desktop (WebRTC)       │
                       panel              └──────────────────────────────┘
```

---

[Continue to Task 1](task-1.md)

