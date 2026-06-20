# Project Lockstep

> A day-of companion for every Headout booking — live on the iPhone & Android Lock Screen, for attractions and live shows.

**▶ Live demo:** https://shashanks1911-pixel.github.io/project-lockstep/

**Hackin '26** · Team **OnlyFixes** · Category: 📈 Move the Needle

---

## What it is

Headout is brilliant at selling the moment — then it disappears. From checkout to the experience itself, the customer is left with an email nobody opens and a head full of questions: when do I leave, what do I wear, do I need an umbrella, where's the gate, where's my ticket. For timed-entry and non-refundable inventory, getting it wrong is a **total loss** — a missed slot, a support ticket, a one-star review, a strained vendor relationship.

Project Lockstep fills that empty **day-of** window with a self-updating Lock Screen activity — **iOS Live Activities** and **Android Live Updates** — built for Headout's two big markets:

- **Experiences / attractions** (Colosseum, Eiffel Tower, Burj Khalifa, and the rest of the catalogue): when to leave or catch the bus, what to wear, umbrella-or-not, what to bring, which gate skips the line, then what to do next.
- **Live entertainment** (Lion King, Wicked, and other West End / Broadway shows): doors vs curtain, the dress code — and the interval. When the break starts it tells you the bar's open and to be back in your seat by 8:55, so nobody misses the start of Act II.

The moat isn't the iOS widget — anyone can build one. It's the **per-experience advice engine** running on Headout's catalogue (10,000+ experiences, 52M+ guests): a single-vertical app — a theatre-only ticketing app, a single attraction's app — can't do dress-code + interval + bus-time + umbrella + skip-the-line across *every* category and city. Headout can, because it already holds the data.

## The lifecycle

The same Live Activity moves through a handful of states across the day, timed off the booking. The states differ by experience type:

- **Show** (Lion King): tonight → time to leave → doors → interval → curtain down
- **Coach trip** (Stonehenge): today → leave now → at the stones → heading back
- **Attraction** (London Eye / Tower / Colosseum): today → leave → entry → in-venue / wrap-up

## Five experiences in the demo

`index.html` is the combined deck. Switch between:

1. **The Lion King** — a West End show (5 states, incl. the interval)
2. **London Eye** — a timed ride (weather read as *visibility*)
3. **Tower of London** — self-paced fortress (sequences you to the Crown Jewels first)
4. **Stonehenge** — coach day-trip (don't miss the coach / be back before it leaves)
5. **Colosseum** — outdoor walking tour abroad

Each also shows the three **Dynamic Island** states (minimal / compact / expanded).

## Bonus: a launchpad for Dex

As a **secondary** boost, on the landmark experiences — Tower of London, Stonehenge, Colosseum — the in-venue state can show a **"▶ Start your Dex tour"** button: the Lock Screen becomes the launchpad for Headout's AI guide (Dex), fired exactly when the guest arrives. A seated show (the Lion King) deliberately skips it. Dex isn't the core of Lockstep — it's a natural extension that makes an existing company bet land.

## Run the demo

- Open **`index.html`** in any modern browser (best in Chrome or Safari).
- On the deck: pick an experience at the top, then tap the state tabs or **"Play timeline."** Open **Tower of London → Inside**, **Stonehenge → At the stones**, or **Colosseum → At the venue** to see the Dex handoff.
- **Tip:** open it full-screen in Safari on a real iPhone — the frosted card over the wallpaper reads almost real.
- Optional: enable **GitHub Pages** (Settings → Pages → deploy from `main`, root) for a shareable live URL.

## Status

Concept + interactive mockup. **No native code yet** (iOS or Android) — the demo runs in the browser. The feature is designed **cross-platform**: **iOS Live Activities** (ActivityKit, iOS 16.1+) and **Android Live Updates** (the equivalent introduced in Android 16, full support in QPR1, 2025), sharing one advice engine with a different render layer. Day-one addressable ≈ the **combined native-app base of ~290K orders/yr** (iOS 197K + Android 93K); iOS is addressable now, Android ramps with OS adoption. See `SUBMISSION.md` for the full pitch, the numbers (on Headout's real device mix), and honest feasibility notes.

## Repo contents

```
index.html        the combined 5-experience deck (main demo)
mockups/          standalone earlier versions
  01-concept.html
  02-lion-king.html
  03-london-experiences.html
SUBMISSION.md     Hackin '26 submission text
```

## Push to your GitHub

```bash
git remote add origin https://github.com/shashanks1911-pixel/project-lockstep.git
git branch -M main
git push -u origin main
```

---

*Concept mockup for internal review. Headout purple `#8000FF`. iOS rendering simplified for illustration. Show names appear as text only; artwork, seats, and the Headout wordmark are original placeholders — not licensed third-party assets.*
