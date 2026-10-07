---
name: credits
description: How the UGC Fans balance works and what to say when credits run out. Use when the user asks about their balance, plan or limits, and whenever a UGC Fans tool answers needs_credits.
---

# Credits

The UGC Fans Studio tools run on UGC Fans' own compute: capturing a website, making a launch film or a sting, editing a film's words, exporting, finishing a clip, transcribing, and sharing files. None of them asks the user to spend credits.

## Reading the balance

Call `ugcfans_get_account` when the user asks. It returns `credits`, `granted`, `spent`, `expires_at`, `plan` and `admitted`. Report the numbers as they are. If `admitted` is false, say the account is not enabled on UGC Fans yet.

## When a tool answers needs_credits

A tool answers `status: "needs_credits"` with `have`, `need` and `plans` when the account cannot run it. Then:

1. Say plainly that this needs more credits than the account has, with the numbers: "This needs 40 credits and the account has 12." When `need` is null, give `have` alone.
2. Say that plans and credits are described at https://ugc.fans/credits and that credits are bought on ugc.fans. Give that link once.
3. Say what was not made.
4. Stop there. Do not retry the call, do not describe or compare plans, do not recommend buying, and never link to a checkout or payment page.
