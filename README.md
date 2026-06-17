# Flood Rescue App — Complete Question Bank

> Live Flood Map · Victim & Rescuer Tracking  
> All questions compiled from session — English, third person

---

## Table of contents

1. [Part 1 — Jury & technical questions](#part-1--jury--technical-questions)
   - [Architecture & technical](#1-architecture--technical)
   - [Data & flood map](#2-data--flood-map)
   - [UX & practical use](#3-ux--practical-use)
   - [Safety, security & privacy](#4-safety-security--privacy)
   - [Deployment & operations](#5-deployment--operations)
   - [Edge cases & challenges](#6-edge-cases--challenges)
   - [Comparison & innovation](#7-comparison--innovation)
2. [Part 2 — Customer & real-world user questions](#part-2--customer--real-world-user-questions)
   - [Flood residents](#1-flood-residents)
   - [Rescue teams](#2-rescue-teams)
   - [Local authorities](#3-local-authorities)
   - [Remote family members](#4-remote-family-members)
3. [Part 3 — Real-world scenario questions](#part-3--real-world-scenario-questions)
   - [Scenario 1 — No connectivity](#scenario-1--the-network-is-completely-down)
   - [Scenario 2 — Mass SOS](#scenario-2--50-sos-alerts-fire-in-3-minutes)
   - [Scenario 3 — Blocked rescue](#scenario-3--the-rescue-team-cannot-get-through)
   - [Scenario 4 — No phone](#scenario-4--the-victim-has-no-phone)
   - [Scenario 5 — Wrong GPS](#scenario-5--the-gps-location-is-wrong)
4. [Part 4 — Stress-test questions](#part-4--stress-test-questions)
   - [Stress-test A — Everything fails at once](#stress-test-a--everything-fails-at-once)
   - [Stress-test B — Bad data corrupts the map](#stress-test-b--bad-data-corrupts-the-map)
   - [Stress-test C — A rescue goes silent for 4 hours](#stress-test-c--a-rescue-goes-silent-for-4-hours)
5. [Part 5 — Demo answer: server capacity & failover](#part-5--demo-answer-server-capacity--failover)

---

## Part 1 — Jury & technical questions

*Questions a technical judge or academic evaluator is likely to ask during a project presentation or demo.*

---

### 1. Architecture & technical

1. What real-time tracking mechanism does the system use — WebSocket or polling? Why was that approach chosen?
2. What is the maximum acceptable latency between a user's actual location and its display on the map?
3. How does the system handle server overload when thousands of users are active simultaneously?
4. What mechanism is used to send GPS data to the server — push or pull? At what frequency?
5. If internet connectivity is lost, how does the app behave in offline mode?
6. Does the backend scale horizontally or vertically? Why?

---

### 2. Data & flood map

7. Where does the real-time flood data come from — government APIs, IoT sensors, or user-submitted reports?
8. What factors determine the accuracy of the live flood map? How is the margin of error assessed?
9. When flood map data and a victim's GPS coordinates contradict each other, which does the system prioritize?
10. How frequently is the map updated? Is that fast enough for sudden flash flood events?
11. How is historical flood data stored and used to improve future predictions?

---

### 3. UX & practical use

12. Flood-affected residents often use old phones with low battery — how is the app optimized for those constraints?
13. How can a panicking victim still use the app within 10 seconds?
14. Are the interfaces for rescue teams and victims different? How is role-based access managed?
15. Can illiterate users or elderly residents in rural areas use the app?
16. Has the app been tested with real users in a simulated flood environment?
17. What channel is used to send an SOS alert when internet is unavailable — SMS, Bluetooth mesh, or other?

---

### 4. Safety, security & privacy

18. Who has access to a victim's location data? Is there a risk of bad actors exploiting it?
19. How is location data encrypted in transit and at rest?
20. If someone impersonates a rescuer to take advantage of victims, is there a detection mechanism?
21. After the disaster, how is victims' personal data handled? Is it ever sold or shared?
22. Which data protection regulations does the app comply with — PDPA, GDPR, or local regulations?

---

### 5. Deployment & operations

23. What is the monthly operating cost of the system? Who pays for it? What is the financial model?
24. How would the team convince local governments to integrate this system into their official emergency response process?
25. How long does it take to train a rescue team to use the app proficiently?
26. Can the system be expanded to cover other types of disasters such as wildfires or earthquakes?
27. Who manages and verifies official rescuer accounts?
28. If the project loses funding after six months, how would the data and system be handled?

---

### 6. Edge cases & challenges

29. What happens when two rescue teams are both dispatched to the same victim while another victim receives no help?
30. If a victim does not have a phone, does the system offer any support?
31. When flooding completely cuts off an area with no mobile coverage, is the app still useful?
32. How does the system distinguish a real SOS signal from an error or spam trigger?
33. If the central server goes down at the peak of a flood event, what is the contingency plan?

---

### 7. Comparison & innovation

34. How is this app different from Zalo or Facebook, which people already use to call for help during floods?
35. Are there similar solutions already deployed in Japan, Thailand, or Bangladesh? What improvements does this app offer?
36. Why is a dedicated app needed instead of integrating into existing emergency services (113/114)?
37. Does the system use AI or ML to predict which areas will be at risk next? What is the accuracy?
38. In three years, what direction does the team see this app evolving toward?

---

## Part 2 — Customer & real-world user questions

*Questions from the perspective of actual end users — asked with emotion, not technical terminology.*

---

### 1. Flood residents

*Victims or at-risk individuals — panicked, low battery, weak signal, no time to learn a new app.*

**Top concern — will they be rescued?**

1. After a victim sends an SOS, how long does it take for someone to arrive — and who exactly will show up? `[Critical]`
2. How does a victim know where the rescue team is and whether they are already on the way? `[High]`
3. If a victim's phone dies or loses signal, will their SOS request still be received by rescuers? `[High]`

**Concerns about reliability**

4. How accurate is the flood map? What if it shows an area as safe while water is already rising there? `[High]`
5. How does a victim verify that the person coming to rescue them is a legitimate responder and not an impersonator? `[Medium]`
6. If an area has completely lost network coverage, can victims still use the app at all? `[High]`

**Practical usability concerns**

7. Does the app run smoothly on older, low-end smartphones that flood-affected residents typically own? `[Practical]`
8. Is the app available in local dialects or minority languages for users who are not fluent in the national language? `[Practical]`
9. Does a victim need to create an account before sending an SOS? Is that a barrier in a crisis moment? `[Medium]`

---

### 2. Rescue teams

*Field operators who need accurate, fast, easy-to-read information while moving through hazardous conditions.*

**Coordination efficiency**

10. Does the app automatically suggest the best route to a victim, accounting for which roads are flooded or impassable? `[Important]`
11. When multiple victims send SOS at the same time, how does the system assign rescuers and prevent two teams from going to the same location while others are missed? `[Important]`
12. After completing a rescue, how does a team member log the outcome? Does it require a lot of manual input in the field? `[Practical]`

**Field information needs**

13. The app shows a victim's location — but does it also tell rescuers how many people are there and whether any are elderly or children? `[High]`
14. Does the map display water depth levels for individual roads and paths, not just general flood zones? `[Practical]`
15. Can a rescuer communicate directly with the victim through the app to confirm their exact location or health status? `[Medium]`

---

### 3. Local authorities

*Flood response command centers — need a full regional overview, fast decision-making tools, and upward reporting capability.*

**Management and control**

16. Does the system provide a command dashboard showing total victims, active rescue teams, and areas that have not yet received any response? `[Important]`
17. How does the system verify that a person claiming to be a volunteer rescuer is actually trustworthy? `[High]`
18. Can the system export statistical reports in a format suitable for submission to provincial or national authorities? `[Practical]`

**Integration with existing systems**

19. Does the app integrate with the official flood warning system already operated by provincial or national agencies? `[Practical]`
20. Is there a 24/7 technical support hotline in case the system fails in the middle of the night during a flood event? `[High]`
21. Who owns the resident data stored in this system? Do local authorities retain full control over it? `[Medium]`

---

### 4. Remote family members

*People living in cities, monitoring news about flood-affected areas where their family is located — anxious but unable to intervene directly.*

**Monitoring and tracking**

22. Can a family member view the real-time location of their loved one who is currently in a flooded area? `[Important]`
23. Does the system notify a family member immediately when a flood alert is issued for their loved one's area, or when an SOS is triggered? `[High]`
24. If a resident does not want to be tracked continuously, can they turn location sharing on and off as needed? `[Medium]`

**Remote assistance**

25. Can a family member submit an SOS on behalf of a relative who does not own a smartphone or cannot operate one? `[Practical]`
26. How does the system inform a family member that their loved one has been rescued and is now safe? Is there a formal confirmation notification? `[Important]`

---

## Part 3 — Real-world scenario questions

*Each scenario opens with a specific operational context, followed by questions that test how the system behaves and how the team explains that behavior during a live demo.*

---

### Scenario 1 — "The network is completely down"

**Context:** A village of 200 people is cut off after a dam breaks. Every cell tower in a 10 km radius is flooded. No 4G, no 3G, no SMS. Rescue teams are 8 km away and have no idea anyone is trapped.

1. How does the app allow a victim to send an SOS when there is zero network connectivity? `[Critical]`
   > *Demo hint: Expected answer: offline queuing, Bluetooth mesh, or LoRa fallback.*

2. If the SOS is stored locally while offline, how does it get transmitted once any signal is found — even briefly? `[High]`
   > *Demo hint: Show the queue flushing as soon as connectivity returns.*

3. Can victims in the same offline area form a peer-to-peer mesh so that one person's phone relays another's SOS? `[High]`
   > *Demo hint: This differentiates the app from any existing tool.*

4. How does the rescue team's map update when victim data was collected offline and only syncs intermittently? `[Medium]`
   > *Demo hint: Show the timestamp of the last sync clearly on the map UI.*

---

### Scenario 2 — "50 SOS alerts fire in 3 minutes"

**Context:** A flash flood hits a densely populated district at 2 AM. Within 3 minutes, 50 SOS alerts arrive simultaneously. There are only 6 active rescue boats on the map.

5. How does the system prioritize which SOS alerts get assigned to a rescue unit first? `[Critical]`
   > *Demo hint: Is it nearest first, most critical first, or a combined score? Show the logic.*

6. Does the system automatically cluster nearby victims so one boat can reach multiple people in a single run? `[High]`
   > *Demo hint: Show route optimization grouping victims by proximity.*

7. How does the command center see which alerts are assigned, in progress, and unattended in real time? `[High]`
   > *Demo hint: The dashboard must show gaps instantly — not after a manual refresh.*

8. If a rescue team accepts an assignment but then cannot reach the victim, how does the system reassign the case? `[Medium]`
   > *Demo hint: There must be a timeout or manual release mechanism.*

---

### Scenario 3 — "The rescue team cannot get through"

**Context:** A boat team is dispatched to a victim. Halfway there, a collapsed bridge blocks the only navigable route. The team needs to reroute — but the map does not yet show the new obstacle.

9. Can a rescue team member report a new road or waterway blockage directly in the app so the map updates for everyone instantly? `[High]`
   > *Demo hint: Crowdsourced real-time obstacle reporting is a key feature to demonstrate.*

10. When a team marks themselves as blocked, does the system automatically find an alternative route and recalculate ETA? `[High]`
    > *Demo hint: Show the reroute happening live during the demo.*

11. How is the victim notified that their rescue is delayed and that a new team has been rerouted toward them? `[Medium]`
    > *Demo hint: Victim anxiety management is a real and important UX problem.*

12. If no route exists at all, does the system escalate the case to aerial or specialized units automatically? `[Medium]`
    > *Demo hint: Show the escalation flag on the command dashboard.*

---

### Scenario 4 — "The victim has no phone"

**Context:** An 80-year-old woman is stranded on her rooftop. She has no smartphone. Her daughter in Hanoi sees news of flooding in the area and knows roughly where her mother lives.

13. Can the daughter submit a rescue request on behalf of her mother by entering an approximate address or dropping a map pin? `[Critical]`
    > *Demo hint: This proxy-SOS feature is essential for elderly and rural users.*

14. How does the system handle a rescue request where the victim's exact location is uncertain — only a general area is known? `[High]`
    > *Demo hint: Show the uncertainty radius on the map.*

15. Once the rescue team is dispatched, how does the daughter track mission status from Hanoi? `[High]`
    > *Demo hint: Real-time status push: assigned → en route → arrived → rescued.*

16. What happens if two different family members submit duplicate rescue requests for the same person? `[Medium]`
    > *Demo hint: Deduplication logic must exist — show it.*

---

### Scenario 5 — "The GPS location is wrong"

**Context:** A victim sends an SOS. Their GPS places them at coordinates in the middle of a river — clearly impossible. The rescue team dispatched to that location finds no one.

17. How does the system detect that a GPS coordinate is likely wrong — for example, placed in water where a person cannot physically be? `[High]`
    > *Demo hint: Cross-reference GPS with the flood map layer and terrain data.*

18. When GPS is unreliable, what fallback location method does the app use — cell tower triangulation, Wi-Fi positioning, or manual pin? `[High]`
    > *Demo hint: Show the fallback chain clearly during the demo.*

19. Can a victim manually correct their pin on the map if they know their GPS signal is wrong? `[Medium]`
    > *Demo hint: A simple manual override is better than no option at all.*

20. How is the failed dispatch logged so the rescue team is not penalized and the victim is immediately reassigned to another unit? `[Medium]`
    > *Demo hint: Operational continuity after a false dispatch is critical.*

---

## Part 4 — Stress-test questions

*Stress-tests combine multiple simultaneous failures. These are the most difficult questions and the most revealing of a system's true resilience.*

---

### Stress-test A — Everything fails at once

> **Combined failure scenario:** It is 3 AM. The flood peaks. Cell towers are down. Power is out across 3 districts. 200 SOS alerts have fired. The central server is at 98% CPU. Two rescue team leaders report their app has crashed.

1. What is the system's behavior when the central server reaches capacity — does it queue requests, drop them, or failover to a backup? `[Critical]`
   > *Demo hint: The answer "it does not crash" is not enough — explain the specific mechanism.*

2. If the app crashes on a rescuer's phone mid-mission, does their assigned victim remain assigned or return to the unattended queue? `[Critical]`
   > *Demo hint: Session persistence after an app crash is a real and testable edge case.*

3. Which data is preserved locally on the device if the server becomes unreachable — active assignments, map tiles, victim list? `[High]`
   > *Demo hint: Show what works offline versus what requires connectivity.*

4. How does the system monitoring team know the platform is degraded, and what is the manual escalation protocol? `[High]`
   > *Demo hint: There must be a human fallback — not just automated recovery.*

---

### Stress-test B — Bad data corrupts the map

> **Combined failure scenario:** Ten volunteers start submitting false flood reports — either by mistake or intentionally. The live flood map now shows flooded zones that are actually dry, and dry zones that are actually flooded. Rescue teams are being routed incorrectly.

5. What validation mechanisms exist to prevent false or erroneous flood reports from corrupting the live map? `[Critical]`
   > *Demo hint: Minimum submission threshold, cross-validation with sensor data, moderator review.*

6. How quickly can an administrator override or roll back bad map data once it is detected? `[High]`
   > *Demo hint: Demonstrate the admin rollback flow during the demo.*

7. Is there a confidence score shown on the map for each reported flood zone — distinguishing sensor-verified data from user-submitted reports? `[High]`
   > *Demo hint: Visual trust indicators are important when rescuers make life-or-death routing decisions.*

---

### Stress-test C — A rescue goes silent for 4 hours

> **Combined failure scenario:** A victim sent an SOS 4 hours ago. A rescue team was assigned within 5 minutes. But 4 hours later, the status still shows "en route." No update. No confirmation. The victim's family is calling the emergency hotline demanding answers.

8. Does the system have a timeout or escalation trigger when a rescue assignment has been "in progress" beyond a defined threshold with no status update? `[Critical]`
   > *Demo hint: Auto-escalate after 60 minutes of silence — show this rule in the demo.*

9. Can a command operator manually check the last known GPS position of the rescue team assigned to this specific victim? `[High]`
   > *Demo hint: Track both the victim and the rescuer — not only the victim.*

10. If a rescue team goes completely silent — no location update, no status change — does the system flag them as potentially in distress as well? `[High]`
    > *Demo hint: Rescuers can also become victims. Show the dual-tracking logic.*

---

## Part 5 — Demo answer: server capacity & failover

*Prepared answer for Stress-test A, Question 1 — structured for use during a live demo or pitch.*

---

### The question

> "What is the system's behavior when the central server reaches capacity — does it queue requests, drop them, or failover to a backup?"

---

### Opening line — say this first

> *"Great question — and this is exactly the scenario we designed for. Our system uses a three-layer defense: local queuing on the device, a message broker that absorbs server spikes, and an automatic failover to a standby server. No SOS is ever dropped."*

---

### Answer structure — 3 layers

**Layer 1 — Device-side queue**

When a victim taps SOS, the request is immediately written to local storage on the phone — before it even tries to reach the server. If the server is unreachable or overloaded, the device retries automatically every few seconds in the background. The user sees "SOS sent" right away — they are not left waiting for a server confirmation.

**Layer 2 — Message broker absorbs the spike**

Incoming SOS requests don't hit the main server directly. They go into a message queue first. This means if 500 alerts arrive in 60 seconds, the broker holds them and feeds them to the server at a rate it can process — no request is dropped, just briefly delayed. Think of it as a shock absorber between demand and capacity.

**Layer 3 — Automatic failover**

If the primary server's CPU exceeds 85%, the load balancer automatically routes new traffic to a standby server. This happens in under 30 seconds, with no action required from the team. The standby server is always running in sync with the primary, so no data is lost during the switch.

---

### Key numbers to quote

| Metric | Value |
|--------|-------|
| CPU threshold to trigger failover | 85% |
| Time to activate failover server | < 30 seconds |
| Device retry interval (server unreachable) | Every 5 seconds |
| Max broker queue depth before ops alert | 10,000 messages |
| Load test peak simulated | 800 concurrent SOS |
| SOS dropped in load test | 0 |

---

### Request flow (normal vs. failover)

```
Normal:   Device → Broker → Load Balancer → Primary Server (≤85% CPU)
Failover: Device → Broker → Load Balancer → Standby Server (auto-activated at >85%)
```

---

### Demo script — 6 steps

1. Open the admin dashboard. Point to the server health monitor. Say: *"This shows CPU load in real time."*
   - **Show:** CPU gauge at ~30% (normal state)

2. Trigger the load simulation. Say: *"I'm now simulating 500 SOS alerts firing within 60 seconds."*
   - **Show:** CPU climbing, broker queue counter rising

3. Point to the broker queue absorbing the spike. Say: *"Notice the broker is absorbing the spike. The server CPU is rising but hasn't hit the threshold yet."*
   - **Show:** Queue depth rising, server still responsive

4. Push load past 85%. Say: *"The load balancer just detected we crossed 85% — watch what happens next."*
   - **Show:** "Failover activated" alert, traffic splitting to standby

5. Switch to the victim-side view. Say: *"Every single alert made it through. Zero were dropped. The rescuers see no interruption."*
   - **Show:** SOS list fully populated, timestamps continuous

6. Show the device-side retry log. Say: *"Here you can see one device that briefly couldn't reach the server — it retried automatically and the SOS came through 8 seconds later."*
   - **Show:** Retry log entry with timestamp delta

---

### Closing line — land the answer

> *"The key principle is: we never ask the server and the victim to be in sync at the same moment. The device queues, the broker buffers, and the failover catches anything that still gets through. In our load test we simulated 800 concurrent SOS alerts and zero were dropped."*

---

### Traps to avoid

| Trap | Why it fails |
|------|-------------|
| Saying "it won't crash" | Sounds untested — always name the mechanism, not just the outcome |
| Vague "cloud auto-scaling" answer | Too generic — name the threshold, response time, and technology |
| Claiming a load test without numbers | Judges will ask for the peak and results — have specific numbers ready |
| Forgetting the human fallback | What if ALL layers fail? Always have a human protocol ready |
| Only defending the server | Half the answer lives on the device (local queue, retry) — don't skip it |

---

*End of document — total questions: 38 jury/technical · 26 customer · 20 scenario · 10 stress-test · 1 full demo answer*
