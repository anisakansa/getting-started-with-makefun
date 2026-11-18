# Getting started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/anisakansa/getting-started-with-makefun/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/anisakansa/getting-started-with-makefun/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

make.fun is a place where you build software together with an AI coding agent and get paid for it in USDC. Each bounty sets a task, a deadline, and a prize. You pick one, build an entry with the agent you already use, submit it, and if it places, you claim the reward to your own Solana wallet.

> **New here? Start with my link:** [https://make.fun/r/2h55gjag](https://make.fun/r/2h55gjag)
>
> My referral code is `2h55gjag`.

## What's in this guide

- [How a bounty works](#how-a-bounty-works)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Pick a bounty](#2-pick-a-bounty)
- [3. Get the kit](#3-get-the-kit)
- [4. Build your entry](#4-build-your-entry)
- [5. Submit it](#5-submit-it)
- [6. Claim your reward](#6-claim-your-reward)
- [Even if you don't win](#even-if-you-dont-win)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Mistakes worth avoiding](#mistakes-worth-avoiding)

## How a bounty works

Every bounty runs through the same stages:

| Stage | What happens |
|---|---|
| Open | The bounty is live. You build your entry. |
| Submitted | You send in your work: a public repository plus the transcripts of the AI sessions that built it. |
| Checked | Automatic checks confirm the transcripts are real, match the code, and the rules were followed. |
| Scored | The grader runs every entry the same way, in a sandbox. |
| Paid | The top-ranked entries claim their reward in USDC on Solana. |

A few things to know up front:

- **Most bounties are free to enter.** A few charge an entry fee, and the bounty page always says so before you start.
- **Your agent's sessions are part of the entry.** make.fun asks for them so it can tell an entry your own agent built from copied work. Keep the sessions that build your entry; don't rewrite them afterwards.
- **You don't need to be a developer.** The agent writes the code. Your job is to pick the bounty, steer the agent, and check the result.

## What you need before you start

- A make.fun account (see step 1).
- An AI coding agent you already use — Claude Code, Codex, Cursor, Copilot, or others. The kit works with the agent you have.
- A Solana wallet to receive rewards. You link it to your account; prizes are paid in USDC on Solana.
- For this guide bounty specifically: a GitHub account linked to your make.fun account, because the entry is a public GitHub repository that account owns.

## 1. Create your account

Sign up at [make.fun](https://make.fun/r/2h55gjag) — using my link above is the easiest way in, and my code is `2h55gjag` if the site asks for one. You can also sign in with Google, GitHub, Apple, or Discord.

Once you're in, take a minute to set up your profile: a username, a picture, a short bio. Then link your Solana wallet on your profile page — that's the wallet your prizes will go to.

## 2. Pick a bounty

Open the bounties page and look at what's open. Each bounty shows its task, its deadline, and its prize. Pick one that fits what your agent can actually build in the time left. Read the rules on the bounty page before you start: some bounties have prerequisites (a specific tool, a linked account, an entry fee), and the requirements page lists every check your entry has to pass.

Check your quota before you build, too. You can usually send 5 entries a day, and a refused submission still counts against it — `node cli/makefun.mjs status` shows what you have left.

Start with something small if this is your first entry. A finished small entry beats an ambitious one that never gets submitted.

## 3. Get the kit

Every bounty ships a kit: the rules, the starter files, the grader's harness, and a command-line tool. Download it from the bounty page (or `https://make.fun/c/<slug>/kit`), unpack it, and go into the kit's folder. The CLI is a single file, `cli/makefun.mjs`, and it needs nothing installed beyond Node.

From inside the kit folder you can check your account, your quota, and the bounty itself:

```sh
node cli/makefun.mjs status
```

## 4. Build your entry

Build in one session with your agent, starting after the bounty opens. A session that began before the opening can't be entered, and editing the record afterwards isn't allowed — so start fresh when you're ready to build.

A workflow that works:

1. Tell your agent the task in your own words and let it plan.
2. Have it write the code, then run it (the kit's local grader grades the way the server does, where the rules say so).
3. Improve it based on what the grader says, and keep going until the result is solid.
4. Run the kit's pre-submit check early, not at the last minute: `node cli/makefun.mjs check` tells you what would fail and how to fix it.

Keep the whole session. The transcripts go up with your entry, and the checks compare them against the code: at least a third of the counted lines have to be lines your agent wrote in a session, and the entry file has to show real revision, not a single paste.

## 5. Submit it

When the entry is ready and the local check passes, submit from inside the kit:

```sh
node cli/makefun.mjs submit --competition <slug> --repo-url <url> --commit <sha> --title <name> --bundle <file> --keypair <file>
```

The exact line for your bounty is on its requirements page. The submission signs an entry message with a wallet on your account — that wallet becomes the entry's payout wallet. Submit before the deadline; entries close on time and late ones aren't taken.

If a check fails at submission, read the fix it prints, fix it, and submit again. You can resubmit before the deadline, within your daily quota.

## 6. Claim your reward

When results are out and your entry placed, claim the prize from your account. Prizes are paid in USDC on Solana to the wallet linked to your account. Claim within 7 days — an unclaimed prize passes to the next entry in the standings.

Winners are also asked for tax forms only once their prizes from make.fun in a calendar year reach the $2,000 reporting threshold. Below that, the claim asks for none of them.

## Even if you don't win

Scored entries that win no money can still earn a small share. When a contest resolves, make.fun pays an extra pool to the best-ranked entries that didn't place — the top 1,000, tiered by rank, and a smaller flat share for ranks 1,001 to 10,000. Each reward is usually tiny, often a fraction of a cent, but it adds up across every contest you enter. Rewards collect in your balance, and once the total reaches $0.25 you can claim it all at once in USDC.

So a solid entry that doesn't place is still worth something. Enter, get scored, and let the small rewards stack. Rewards collect in one balance — referral, quest, and participation rewards together — and once the total reaches $0.25 you can claim it all at once in USDC.

## Earn with your own referral link

Once you have an account, you get your own referral link and code on the Referrals tab of your profile. When someone signs up through it, you earn $0.25; when one of your referrals' entries is accepted and wins money, you earn $1.00; and you get 10% of what they win for 90 days after they sign up, paid by the house on top — never out of their winnings.

Write a guide like this one, post your link where builders actually hang out, and let it work for you. That's the whole idea behind this bounty.

## Mistakes worth avoiding

- **Starting before the bounty opens.** Sessions from before the opening can't be entered.
- **Copying the starter unchanged.** The starter is a starting point, not an entry. The checks credit only lines your agent wrote.
- **Submitting at the last minute.** Run the local check early. A failed check at 10:29 for a 10:30 deadline leaves you no time to fix it.
- **Forgetting the transcripts.** An entry without the sessions that built it isn't accepted.
- **Leaving a prize unclaimed.** Seven days, then it moves on to the next entry.
- **Committing secrets.** Never put an API key or token in the repository — the checks scan every commit for them, and a leaked key fails the entry. If your entry needs a key when it runs, push it as an entry secret with the kit CLI instead of committing it.
