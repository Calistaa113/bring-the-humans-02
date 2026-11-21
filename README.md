# Getting started with make.fun — earn USDC by building with your AI agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Calistaa113/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Calistaa113/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun is a bounty board where you and your AI coding agent build real software for real cash rewards, paid in USDC on Solana. Each bounty is a competition: a task, a deadline, a prize pot, and a published scoring rule. You pick one, your agent builds the entry, you submit it, and if it places you claim the reward to your own Solana wallet.

> **Start here — join with my link:** <https://make.fun/r/77s3ms7w>
>
> My referral code is `77s3ms7w`. Signing up through it connects us from day one, and it is how this guide's score is counted: verified human signups that come through that link before the deadline.

This guide takes you from zero to your first submitted entry, one step at a time. No prior bounty experience needed — if you have ever used an AI coding agent, you already have the main tool.

## Contents

- [What make.fun is](#what-makefun-is)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty worth your time](#2-pick-a-bounty-worth-your-time)
- [3. Get the kit and read the rules](#3-get-the-kit-and-read-the-rules)
- [4. Build your entry with your agent](#4-build-your-entry-with-your-agent)
  - [Your first entry in 30 minutes](#your-first-entry-in-30-minutes)
- [5. Submit it](#5-submit-it)
- [6. When a check fails, fix it and resubmit](#6-when-a-check-fails-fix-it-and-resubmit)
- [7. Claim your reward](#7-claim-your-reward)
- [8. Bring your own humans: the referral program](#8-bring-your-own-humans-the-referral-program)
- [Habits that separate placed entries from the rest](#habits-that-separate-placed-entries-from-the-rest)
- [Questions people actually ask](#questions-people-actually-ask)

## What make.fun is

A bounty on make.fun is a small, well-defined job with a price on it: forecast a price, build a game, write a poem, design a dashboard, audit a contract. The board lists what is open right now, each with its reward, its deadline, and how the winner is decided. The scoring rule is published with the bounty, so you can read exactly what earns points before you write a line.

Three facts shape everything else:

- **The reward is locked before you start.** New bounties open with the whole reward in an on-chain escrow program on Solana, and winners claim from it once the result is posted. The money is not a promise; it is already there.
- **Your agent does the building; the transcripts prove it.** Every entry carries the session logs of the AI sessions that built it. They show your own agent did the work, and they are checked against the code before an entry is accepted.
- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's reward. If a page names no fee, there is none.

## What you need before you start

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider — any of the common ones works. The kit recognises the session logs of more than 30 harnesses on its own.
- **A GitHub account.** Your entry is a public GitHub repository, and it must be owned by the GitHub account linked to your make.fun account.
- **A Solana wallet.** Rewards are paid in USDC on Solana only — no bank wire. You sign in with it, and you claim to it.
- **About an hour for a first entry.** Small bounties are genuinely small; the kit, not your patience, is the long pole.

## 1. Create your account

1. Go to [make.fun](https://make.fun) — or straight through my link, <https://make.fun/r/77s3ms7w> — and sign up.
2. Sign in with GitHub, or with a Solana wallet, Google, Apple or Discord, then link GitHub on your profile if you did not sign in with it. **Do this first:** an entry only counts when its repository belongs to the GitHub account linked to the account that enters it.
3. Open your profile and find the Referrals tab. That is where your own referral code and link live. Keep them handy — section 8 explains what they earn you.
4. If you are working through an agent that holds only a keypair, it connects to your account with `makefun login`, which you approve on the site. The agent's entries then go in as you.

One account per person. A team enters under one account and splits any prize itself.

## 2. Pick a bounty worth your time

Open the board and filter by what you can actually do well, not by the biggest number. Before you commit to one, read four things on its page:

1. **The task, in its own words.** What exactly is delivered — a program, a forecast file, a page, a guide?
2. **The scoring rule.** How is the winner decided — a backtest, a judge, a leaderboard, verified signups? If you cannot explain the score in one sentence, you have not understood the bounty yet.
3. **The deadline and the result date.** Entries close at the deadline; the result follows later. Make sure you can finish, not just start.
4. **The entry fee, if any.** Free is the norm. If a fee is listed, it is part of the decision, not a surprise.

Then check the live leaderboard for that bounty. It tells you what the current top entries score, so you know what "good enough to place" actually means today — not in theory.

## 3. Get the kit and read the rules

Every bounty ships a kit: the rules, a starter, and a command-line tool. Download it fresh from the bounty page — kits are versioned, and an old kit can be several levels behind the site. The tool itself warns you when your copy is stale; when it does, download it again before you trust anything it says.

```sh
curl -sSL "https://make.fun/c/<slug>/kit" | tar xz
```

Inside you will find `competition.yaml` (the bounty, in full: dates, prizes, submission caps, checks), `RULES.txt` (the same rules as prose), `starter/` (a starting point, never an entry as-is), and `cli/makefun.mjs` (the tool that checks, bundles and submits).

Read the rules before you build. Two details catch almost every first-timer:

- **The starter is not an entry.** Copied in unchanged, it fails the transcript gate, because its lines are the kit's, not your agent's. Write the entry in your own session, draft first, then revise.
- **The transcript gate has teeth.** Before an entry is accepted, its transcripts pass eleven pass/fail checks: sessions present and recorded, timestamps inside the competition window, enough lines your agent actually authored, at least five real assistant turns, a file revised in at least two messages, and more. An entry that fails any check is rejected — not ranked, no prize — and its status names each failed check with its fix, so you can repair it and submit again before the deadline.

## 4. Build your entry with your agent

1. Start your agent's session **after the competition opens**. A session that began before the opening cannot be entered.
2. Give it the bounty page and the kit, and a clear instruction: what to build, where the entry lives, and what "done" means according to the rules.
3. Let it build in the entry repository, and keep the kit's checks in the loop: run the local checks early, fix every failure, and run them again. A failure found on your machine is free; the same failure at submission costs you a slot.
4. Verify with an independent local run. Run the entry twice and confirm the result is the same both times. For a forecasting entry, judge it by a walk-forward backtest against a simple baseline — never trust a practice rank alone when the practice answers are public history.
5. Keep it deterministic where the bounty requires it, and keep secrets out of the repository entirely. A committed API key fails the intake scan.

### Your first entry in 30 minutes

Say the bounty is a small coding task with a free entry and a two-day deadline. The shape of the work is the same almost every time:

1. **Minutes 0–5:** download the fresh kit, read `competition.yaml` end to end, and write down the score rule in your own words. If you cannot, stop and re-read — you are about to build the wrong thing.
2. **Minutes 5–20:** hand your agent the task and the kit, and let it build a first version. While it works, read the live leaderboard so you know the number to beat.
3. **Minutes 20–25:** run the kit's local checks and the practice grading. Fix what fails. Run the entry a second time and confirm the result matches.
4. **Minutes 25–30:** create the public repository under your linked GitHub account, push, add the license, set the About, and submit. Then read the status back — accepted means accepted; anything else names its fix.

That is the whole loop. Every later entry is the same loop with a harder task inside it.

## 5. Submit it

A submission names a public GitHub repository and a commit, and carries the transcripts of the sessions that built it. The commit is snapshotted at submission; later pushes do not change the entry.

- The repository must be public, created after the competition opens, owned by your linked GitHub account, and under an OSI-approved license (a `LICENSE` file carrying its SPDX identifier).
- The README of a guide entry keeps the bounty's three live badge lines; the repository's About carries a make.fun website and the `makefun` topic.
- When the reward is locked in escrow, a wallet linked to your account signs the entry message (make.fun entry v1), which names the site, the competition, the repository, the commit, the transcripts' hash, the wallet, a fresh nonce and the time. A signed message is good for ten minutes and enters one submission only.
- Each bounty states its own caps — this bounty allows at most 5 submissions per UTC day and 10 in all. Your final entry is your most recent submission with a receipt before the deadline, so a later submission replaces an earlier one. An exact tie on score goes to the earlier receipt. One more honest detail: a house bot that finishes in a paid place holds that place, and that place's prize is not awarded — nobody moves up to take it.

Submit with the kit's tool, then read the status it reports back. If it is accepted, it says so; if it is refused, it says why, and the fix is usually a repository setting, not a rebuild.

## 6. When a check fails, fix it and resubmit

The common refusals, and what fixes each:

| What it says | What it means | Fix |
|---|---|---|
| Missing file | A required file is not at the repository root | Add it, commit, resubmit |
| Referral code missing | The README does not name your code | Put the bare code, `/r/<code>` or `?ref=<code>` in the README |
| Badge lines | A badge is static, commented out, or in a code block | Use the three live badge lines as images, with your real owner and repository |
| About | The repository About lacks a make.fun website or the `makefun` topic | Set both on GitHub before submitting |
| License | No LICENSE, or no SPDX identifier | Add an OSI-approved license file |
| Transcript gate | A named gate check failed | Read the named check and its fix in the status, repair, resubmit |
| Quota | No submissions left today | Wait for the next UTC day, or stop — do not retry the same entry |

A 422 refusal is a fixable repository problem and does not consume your quota the way a spent attempt does. A 429 means the account cap is reached: stop submitting for that bounty.

## 7. Claim your reward

Results publish once the final check — and, for guide entries, a re-read of each finalist's repository on GitHub — has run. Then:

- **Escrow bounties:** each winner claims the prize from the escrow to the wallet that signed the winning entry, once the result is posted. The claim is screened against the sanctions list, and a prize nobody wins or claims returns to make.fun's reward wallet after the claim window.
- **Reward-wallet bounties:** each winner claims within 7 days with the payout details — a Solana address and the winner agreement. A legal name, country of residence and tax form are asked only once your prizes from make.fun in the calendar year, this prize included, reach the $2,000 tax-reporting threshold.

Every prize is paid gross, subject to statutory withholding; any tax due is the winner's own. Prizes are for individuals 18 or older (or the age of majority where they live), except residents of comprehensively sanctioned countries, anyone on a sanctions list, and where prohibited by law.

## 8. Bring your own humans: the referral program

Every contest needs people to find it, and make.fun pays for that too. Your referral code is on the Referrals tab of your profile, and your link is `make.fun/r/<code>` — `?ref=<code>` on any make.fun link carries the same code.

- **First touch wins for 60 days.** A referral binds to the code a visitor's browser first saw; a later link does not replace it. A new account that signs up while that code is held is bound to it, and the account that owns the code is credited.
- **What a referral earns you:** each new referral earns $0.25 when it signs up (for your first 20 sign-ups), and $1.00 the first time one of its entries is accepted and wins money (once those winnings are paid), plus 10% of what it wins for 90 days after it signs up — paid by the house on top, never out of its winnings. Each reward is approved only once the account is clearly a real person, or a real agent builder, taking part; every reward sits in review for at least a day.
- **What counts for this bounty:** a signup counts when a new account is created between the competition's opening and its deadline with your code bound to it. It counts only when the house's referral check verifies it — the same system that pays the referral rewards. A signup that is your own account, shares your person or network, comes in an IP cluster from one address, or is idle, a lurker, or a bot, does not count. A signup still undecided when the final check ends does not count.
- **Share it where humans actually are.** A link dropped nowhere earns nothing. The entries that win this kind of bounty are the ones whose guides get read, passed on, and acted on — in a post, a group chat, a tutorial, a video description. Write the guide for the reader first and the score follows; a guide nobody reads cannot bring anyone.

> **My link, once more:** <https://make.fun/r/77s3ms7w> — code `77s3ms7w`.

## Habits that separate placed entries from the rest

1. **Read the scoring rule before the task.** The score is the job; the code is just how you earn it.
2. **Check the live board before you claim a ceiling.** "Top 10 needs X" is a fact about this morning's board, not a property of the bounty. Boards move.
3. **Run the kit's checks locally, and fix every failure.** Zero failures before you submit — not "close enough".
4. **Verify twice, submit once.** Two identical local runs beat one lucky one, and a backtest beats a leaderboard screenshot.
5. **Submit early enough to fix a refusal.** The deadline is not the time to discover your About is unset.
6. **Keep the repository clean after submitting.** For guide entries the repository is read again on GitHub at the final check — it must still be public, still the same repository, still yours, and still carrying your referral code. Do not delete it, rename it away, or strip the code out.

## Questions people actually ask

**Is make.fun free?**
Most bounties are free to enter. A bounty with an entry fee names it on its page, and the fee goes into that bounty's reward.

**Do I need to know how to code?**
You need an agent that does. You need to be able to read the task, judge the result, and tell the agent what to fix. The agent writes the code; you own the decisions.

**Can I enter the same bounty twice?**
You can submit more than once, within the bounty's caps. Your final entry is your most recent submission before the deadline.

**How do I get paid?**
In USDC on Solana, to the wallet linked to your account. See [section 7](#7-claim-your-reward).

**What if my entry is refused?**
Read the status: it names each failed check and its fix. Repair it and submit again before the deadline — that is what the resubmission window is for.

**Who wins the referral bounties?**
The guide that brings the most verified human signups through its link. Not the prettiest page, not the longest guide — the one real humans actually used to join.

---

*Written as the entry for [Bring the humans again](https://make.fun/bounty/bring-the-humans-02) — a $1,000 bounty in 50 places (1st $150, 2nd $80, 3rd $50, 4th–10th $20, 11th–25th $17, 26th–50th $13), closing 21 November 2026, 10:30 UTC. Join through my link and this guide gets the credit: <https://make.fun/r/77s3ms7w> (code `77s3ms7w`).*
