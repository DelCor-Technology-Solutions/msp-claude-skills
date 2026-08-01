# Negotiation Playbook: After the Proposal

This file governs everything that happens between "Proposal Sent" (pipeline stage 5) and a signed
Order or a logged Closed Lost. It covers the client who comes back with a counter, the client who
asks for a better number, and the client who says no because of cost. The objection-handling guide
covers "too expensive" *before* a proposal exists; this playbook takes over once a real number is
on the table.

**Boundary notes:**

- Every number still comes from msp-pricing. This file decides *which lever to pull and in what
  order*; the configurator produces the actual figure. Never eyeball a revised price.
- If the pushback is about contract language (liability, termination, non-solicit, venue), that is
  not a price negotiation. Hand off to msp-legal, which owns the clause playbook.
- The floor is the floor. Nothing in this file authorizes quoting below it without owner sign-off.

---

## The Governing Principles

1. **Diagnose before you concede.** A counter-offer is information, not a demand. Before touching
   the number, find out what is actually driving it: budget reality, a competing quote, a
   negotiating habit, or a value gap you failed to close. Each has a different answer, and only
   one of them involves the price.

2. **Never lower the price without changing something.** Every reduction is attached to a reason
   the client can see: a longer term, a removed block, a waived onboarding fee. A price that drops
   just because they asked teaches them the first number was padded, and every future renewal
   becomes a haggle. Scope moves, terms move, the integrity of the number does not.

3. **Concessions shrink and slow.** If you move twice, the second move is smaller than the first
   and arrives more slowly. Equal or growing concessions signal there is always more; shrinking
   ones signal you are near the end.

4. **Never bid against yourself.** One revised proposal, maximum, without a counter from them. "Can
   you sharpen your pencil?" gets a question back, not a new number: "Happy to look at it. What
   number were you hoping to see, and what would you be comfortable giving up to get there?"

5. **Get something for everything.** A concession trades for commitment: a longer term, a signature
   date, the full option instead of the lean one, a referral introduction. "If I can get you to
   $X, are you ready to sign this week?"

6. **Present revised numbers live, every time.** The same rule as the original proposal. An emailed
   lower number is a coupon; a walked-through revision is a decision. If they went dark, the new
   number is the reason for the call, not the content of the email.

7. **Protect the relationship at every exit.** Most "no" answers are "not now." Walk away warm,
   log the reason, and be the obvious first call when their situation changes.

---

## The Concession Ladder (pull levers in this order)

When a client pushes for a better number, work down this list. Do not skip steps, and do not
combine steps unless trading for a signature on the spot.

**Step 0: Ask, then re-anchor on value.**
No lever yet. "Help me understand: is it the monthly number itself, the first-month total with
onboarding, or comparing it against something else?" Then restate what the number buys in their
words from discovery. A surprising share of pushback dissolves here, because the objection was
never really the price.

**Step 1: The term ladder.**
The built-in, pre-approved discount. Committing to 2, 3, or 5 years steps the monthly down (4% of
the 1-year opening per additional year, per msp-pricing; the configurator prints the ladder).
Frame: "The monthly number you're looking at is the one-year price, which is the highest price we
have. If you're comfortable committing longer, the number comes down." This is the only lever that
lowers MRR, and it costs them commitment, which is exactly the trade you want.

**Step 2: The onboarding fee waiver.**
The named closing tool. If the sticking point is the first-month total rather than the monthly,
concede the onboarding fee before ever touching MRR: 50 to 100% off the onboarding SOW, only with
a signed Order of at least one year on or before the SOW date, with the clawback in the Order.
Frame: "Sign the one-year agreement and onboarding is on us." Never frame it as a discount ladder
on the monthly.

**Step 3: Re-scope.**
If the budget is genuinely short of the recommended option, move them to the lean option or build
a new lean option, removing real blocks: fewer on-site hours, deferring the camera fleet, phasing
mobile devices in later. The price falls because the scope fell. State it exactly that way: "Here
is a version that fits that budget. Here is what it does not include, and here is what I'd add
back first when you're ready." Two hard limits: never re-scope below responsible coverage
(endpoint protection stays on every managed computer), and response time never varies, so speed
is never what gets removed.

**Step 4: Phase the start.**
Same scope, staged onboarding: start with the core users and servers this quarter, add the second
site or the device fleet next quarter. The end-state MRR is unchanged; the early invoices are
smaller. Useful when the objection is cash-flow timing, not value.

**Step 5: Hold, and be ready to walk.**
If they are still pushing below what the levers produce, the deal is below the floor or the
$1,000 minimum (a shipped example default; set your own in msp-pricing), and the answer is a warm
no. "I'd rather tell you honestly that we can't do it well at that number than sign you up for
something that underserves you." Walking away cleanly wins more revivals than a strained yes wins
renewals.

**Never on the menu:** ad-hoc percentage discounts on MRR, waiving the multipliers, a cheaper
short-term deal, response-time tiers, matching a competitor's number line for line, or any figure
below floor. If a client asks for one of these, the answer is a redirect to a lever above.

---

## Presenting a Revised Number

Mechanics for the re-quote conversation, whichever lever produced it:

1. **Re-run the configurator first.** New term, new scope, or new counts means a fresh
   `price_quote.py` run. The revised number gets the same floor discipline as the original.
2. **Open with what changed, not with the number.** "You asked if we could get closer to $X. I
   looked at two ways to do that." Then the lever, then the number, then stop talking. The
   silence rule applies to revisions exactly as it did to the original.
3. **Keep the original visible.** The first proposal is the anchor; the revision is positioned
   against it. "The full option is still $Y and still what I'd recommend. Here's the version
   that meets your budget and what it trades away." Clients who see the delta often climb back
   up to the recommended option on their own.
4. **Attach the close.** A revised number always travels with a commitment question: "If this
   version works, can we get the Order signed by Friday?" A revision without a close is just a
   lower price waiting to be negotiated again.
5. **Put a shelf life on it in plain words.** Not fake urgency: real scheduling truth. "I'm
   holding the onboarding slot and these counts through the end of the month; after that I'd
   need to requote." Counts drift, wages drift, and the waiver is tied to dated paper anyway.

---

## Counter-Offer Scenarios

**"Can you do $X?" (a specific number)**
Do not answer the number first. "Maybe. Tell me how you got to $X?" If it maps to a real budget,
work the ladder toward it and say plainly whether the levers reach it. If it does not reach:
"Honest answer: I can't get to $X with everything in here. I can get to $Y with [lever], or I
can build you a version that hits $X with [reduced scope]. Which is closer to what you want?"

**"Your competitor quoted less."**
Never match blind. "That may be a fair price for what they quoted. Can I take a look at what's
in it?" Compare scope, not totals: seat counts, what is actually managed versus monitored,
onboarding, after-hours coverage, and what happens when something breaks. If their quote is
genuinely comparable and lower, sell the difference you actually have (accountability,
documentation, the response commitment in writing). If the client just wants the cheaper one,
let them take it warmly and log the revival triggers below. Competing on price against a
commodity quote is how the floor dies.

**"Take 10% off and we'll sign today."**
The signature is the trade, so use a lever, not a discount: "I can't cut the monthly 10%, that's
not how our pricing works. What I can do today: [term ladder step or onboarding waiver]. That's
worth more than 10% in the first year anyway. Do we have a deal?" Run the math live; the waiver
usually beats their ask.

**"We don't need everything in here."**
The best counter-offer you can get, because it is a scoping conversation wearing a discount
costume. Walk the blocks together, remove what genuinely does not fit, keep what protects them,
and requote. The price drops because scope dropped, and the client feels heard instead of
bargained with.

**The nibble (after verbal yes: "just throw in onboarding / a few extra seats").**
Small asks after agreement are a test, not a dealbreaker. Trade or decline cheerfully: "I can't
add seats for free, they carry real cost. What I can do is [waiver if not yet used / lock these
counts through signing]." If it was already conceded once, hold: "That one's already in the deal."

**Procurement or a board is now involved.**
The new party has not heard the value story, only the number. Offer to present, not to re-paper:
"Happy to walk your partner/board through what this covers; numbers without context always look
high." Same proposal, new audience, live presentation. Do not send a discounted version to a
person you have never spoken to.

---

## The No-Due-to-Cost Playbook

When the answer after a proposal is no and the stated reason is price:

**1. Get the real reason before accepting the stated one.**
"Completely fair. Before I close the file, can I ask: if the number had been half, would this
have been a yes?" A hesitation means the objection was never only price (timing, the incumbent,
a partner's veto, change fatigue). Handle the real one; the objection-handling guide has the
tracks.

**2. Make one honest re-scope offer, once.**
If cost is genuinely it, offer the lean rebuild (Concession Ladder step 3) a single time: "Would
it be worth 15 minutes to see what a leaner version looks like before you decide?" If the answer
is still no, stop selling. A second retry converts a warm no into an annoyed one.

**3. Leave the break-fix door open.**
A real, honest fallback that costs you nothing: "If a managed plan isn't in the budget this year,
you can still call us when something breaks, at our non-contract rates. No agreement needed."
Say plainly what it does not include: nothing proactive, no response commitment, no flat fee.
Break-fix clients who feel the difference are next year's managed clients. Rates per
`break-fix-rates.md` in msp-pricing; never discount those either.

**4. Close warm and log it.**
Move the deal to Closed Lost with reason "price" (or the real reason from step 1) the same day.
Send a two-line thank-you with no pitch: "Thanks for the serious look. If anything changes on
your side, you know where I am." Log any dates you learned: their budget cycle, the incumbent's
renewal, the lease on the office they are outgrowing.

**5. Schedule the revival touch.**
Set a follow-up at 90 days, or timed to a logged date if you have one. The touch is a reason,
never a re-pitch: something changed on their side ("saw you're hiring, congrats"), something
useful from you (a relevant advisory you already send clients), or a plain check-in ("how did
the busy season treat the systems?"). One touch per quarter, warm and short, until they engage
or ask you to stop.

**6. When they come back, requote fresh.**
A revived deal gets a fresh discovery delta ("what's changed since we last talked?") and a fresh
configurator run with current counts and current rates. Do not resurrect the old PDF: headcount
moved, the sheet may have moved, and a stale number either underprices the deal or contradicts
the new one. If the new number is higher than the old proposal, say so before they notice:
"You've grown since we quoted this, so the number moved with you."

**Revival triggers worth watching for logged Closed Lost deals:** a security incident in their
industry or their inbox, a cyber-insurance renewal, the nephew or the incumbent leaving, a new
office or an acquisition, hiring sprees, and compliance pressure arriving (new contract, new
regulator, new insurer). Any of these is a same-week call, not a scheduled touch.

---

## Quick Reference

| Situation | First move | Lever |
|-----------|-----------|-------|
| "Can you do $X?" | Ask how they got to X | Ladder, then re-scope |
| First-month total too high | Split monthly from onboarding | Onboarding waiver |
| Monthly too high, real budget | Confirm the budget number | Term ladder, then re-scope |
| Competitor quoted less | Compare scope, not totals | Sell the difference or walk warm |
| "Discount and we sign today" | Trade, never discount | Waiver or ladder, run math live |
| "We don't need all this" | Scope walk-through together | Re-scope, requote |
| Nibbling after yes | Trade or hold cheerfully | Count lock, waiver if unused |
| No due to cost | Test if price is the real reason | One lean re-scope, then break-fix door |
| Deal gone dark post-proposal | Call with a reason, not a nudge | Revision presented live |
| Revived deal returns | Fresh discovery delta | Fresh configurator run |
