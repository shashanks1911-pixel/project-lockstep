# Hackin '26 | Submission

**Team name:** OnlyFixes

**Team members:** Shashank Shekhar, Surya Shikhar

**Github Repo Link:** _[your repo URL]_  <!-- fill in -->

**Project name:** Project Lockstep _(working title)_

---

## What problem are you solving?

Headout is brilliant at selling the moment — then it disappears. From checkout to the experience itself, the customer is left with an email nobody opens and a head full of questions: *when do I leave, what do I wear, do I need an umbrella, where's the gate, where's my ticket.* For timed-entry and non-refundable inventory, getting it wrong is a **total loss** — a missed slot, a support ticket, a one-star review, a strained vendor relationship.

Project Lockstep fills that empty **day-of** window with a self-updating Lock Screen activity — **iOS Live Activities** and **Android Live Updates** — built for Headout's two big markets:

- **Experiences / attractions** (Colosseum, Eiffel Tower, Burj Khalifa, and the rest of the catalogue): when to leave or catch the bus, what to wear, umbrella-or-not, what to bring, which gate skips the line, then what to do next.
- **Live entertainment** (Lion King, Wicked, and other West End / Broadway shows): doors vs curtain, the dress code — and the interval. When the break starts it tells you the bar's open and to be back in your seat by 8:55, so nobody misses the start of Act II.

The moat isn't the widget — anyone can build one. It's the **per-experience advice engine** running on Headout's catalogue (10,000+ experiences, 52M+ guests): a single-vertical app — a theatre-only ticketing app, a single attraction's app — can't do dress-code + interval + bus-time + umbrella + skip-the-line across *every* category and city. Headout can, because it already holds the data.

## What metric does this move, and why does that metric matter?

Primary metrics: **on-time arrival (no-show / late rate), support deflection, Repeat CVR, and app adoption (mobile-web → app).** (Framing: this is a *post-purchase* surface, judged on Repeat CVR + Recco CTR, **not** funnel CVR.)

Why they matter: the Lock Screen is the most valuable real estate on the phone, and a persistent, well-timed companion changes *behaviour* — leaving on time, coming back from the interval, rebooking at the peak — in a way email and push can't. It produces on-time, prepared guests, which protects CSAT and vendor relationships (e.g. the Delfont Mackintosh West End partnership). And because these surfaces are app-exclusive, a genuinely useful companion is a real reason to install — today the apps are only **6.5% of orders combined** (iOS 4.4% + Android 2.1%) vs **66.8%** on mobile web.

Proxy metric for the experiment: **opt-in rate + tap-through on the "open ticket" / "what's next" card + on-time-arrival delta** on a timed-entry POI.

## If you nail it, what materially changes? (put a number on it)

Anchors: $130M revenue (2024), ~$1B GBV target (2026), 52M+ guests. Real device mix (last 12 months): **iOS app = 197,230 orders (4.4%)** and **Android app = 93,156 orders (2.1%)** — a **combined native-app base of ~290K orders/yr** that this ships to. Mobile web = **3.0M orders (66.8%)**.

The feature is **cross-platform from day one** — iOS Live Activities + Android Live Updates (the equivalent introduced in Android 16) — so it's not iPhone-only. _(Caveat: Android 16 / QPR1 adoption is still ramping through 2026, so the Android slice grows as the OS rolls out; iOS 16.1+ is near-ubiquitous and immediately addressable.)_

**Short term (0–4 weeks):** post-purchase presence goes from **zero to a live, on-device companion**, demoed end-to-end across both markets — a West End show (**The Lion King**, with the interval beat) and attractions (**London Eye, Tower of London, Stonehenge, Colosseum**) — with all three Dynamic Island states and every tip mapped to real booking-page data. (Demo shown on iOS; Android Live Updates is the parallel build.)

**Medium term (1–3 months):** on the **~290K combined native-app base**, a **~20% relative cut in timed-entry no-shows ≈ ~1,400 saved bookings/yr**, plus support deflection (~$58K) and a modest rebooking lift (~2,900 bookings/yr ≈ ~$260K GBV, _illustrative — pending the real repeat-rate baseline_) — a low-to-mid hundreds-of-$K floor, dominated by CSAT and vendor value the model doesn't capture. The advice engine becomes a reusable internal service. **App adoption** is the bigger lever — and now it's platform-complete: the install hook ("download for a live companion") works for the **entire 3.0M mobile-web base regardless of phone OS** (iPhone users get Live Activities, Android users get Live Updates), instead of only the iPhone slice. _(The companion doesn't acquire users itself; it's the payload that makes the install pitch worth acting on.)_

**Long term (3–6 months):** the companion becomes the **connective tissue of the day-of journey** across the 10,000+ catalogue and both markets, on **both platforms** plus Apple Watch — and every lever above scales as Android 16 adoption climbs off its current floor. The moat (cross-category advice engine + Lock-Screen surface) puts any competitor starting then 6 months behind.

## Bonus: a launchpad for Dex

As a **secondary** boost, the in-venue state can hand the guest straight into **Dex**, Headout's AI guide, in one tap — turning the Lock Screen into Dex's launchpad at the exact moment it's useful (landmarks only; a seated show skips it). Dex isn't the core of Lockstep; it's a natural extension that makes an existing company bet land.

## Which award category are you going for?

📈 **Move the Needle** — on-time arrival, app adoption, repeat rate, CSAT.

## Proof of work

Interactive mockup deck, demoed on laptop — **5 experiences across both markets** (Lion King, London Eye, Tower of London, Stonehenge, Colosseum), full day-of lifecycle, all three Dynamic Island states, every tip mapped to real booking-page data (plus an optional **"Start your Dex tour"** handoff on landmarks). iOS shown; Android Live Updates is the parallel surface.

- Demo deck: `index.html` (this repo)
- Hosted demo / pitch card: _[link]_  <!-- fill in -->

---

### Honesty notes (carry into Q&A)

- **No native code yet** (iOS or Android) — browser mockup on a laptop, not built on ActivityKit / Android notifications. (We deliberately did **not** claim the *Root Access / deep-in-the-stack* category.)
- **Cross-platform, but Android ramps.** iOS Live Activities are addressable now; Android Live Updates need Android 16 (full support in QPR1, 2025), so the Android share grows over the next 12–18 months as the OS rolls out.
- **The Dex handoff is a represented launch point** (a button), not a live integration — phrase it as *"Dex-ready."*
- **The rebooking number is illustrative** until the real same-trip repeat-rate baseline is pulled from Mixpanel.

### Feasibility (for technical questions)

- **iOS — Live Activities** (ActivityKit, iOS 16.1+): active up to ~8 hours, ~12 hours on the Lock Screen. **Push-to-start** (iOS 17.2+) launches it on the day without opening the app. Updates are server-driven via APNs — a handful per day (ready -> leave -> entry -> wrap-up / interval), low-frequency, no battery or rate-limit issues.
- **Android — Live Updates** (Android 16; full support in QPR1, 2025): "promoted" progress-style notifications shown prominently on the lock screen, always-on display, and as a status-bar chip — the parallel surface to Live Activities. Note: branding/colour control is tighter than iOS, so the Android card looks slightly more system-styled.
- **The advice engine** = experience metadata Headout already holds + venue rules + a live weather lookup, capped at ~3 tips so the card never clutters. Shared across both platforms; only the render layer differs.
