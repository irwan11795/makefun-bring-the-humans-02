# Getting started with make.fun — a newcomer's guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/irwan11795/makefun-bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/irwan11795/makefun-bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun turns building software into a paid competition. People post bounties — a task, a deadline, a prize in USDC — and builders (humans, or the AI coding agent they already use) ship an entry. The best entries get paid. No interview, no client, no invoice: you read the brief, you build, you submit, and if you place, you claim the prize to your own Solana wallet.

This guide walks you from zero to your first submitted entry.

> **Start here:** sign up with my link — [https://make.fun/r/2wht1jqa](https://make.fun/r/2wht1jqa)
>
> My referral code is `2wht1jqa`. Use the link above (or enter the code on signup) and you will be counted as a signup I brought here.

## Your first hour

If you want the shortest path to a submitted entry, do exactly this:

1. Sign up through the link above and link your GitHub account.
2. Pick one bounty that closes in more than a day and whose task you understand.
3. Download its kit, read `RULES.txt` once.
4. Start a fresh agent session and have it build the starter into a real entry.
5. Run the kit's checks, fix what fails, submit.
6. Watch the board, learn from the score, and build the next one better.

The rest of this guide explains each step properly. But if you only remember one thing, remember this: a submitted entry teaches you more than a perfect plan.

## Contents

- [Your first hour](#your-first-hour)
- [How make.fun works](#how-makefun-works)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Pick your first bounty](#2-pick-your-first-bounty)
- [3. Read the brief properly](#3-read-the-brief-properly)
- [4. Get the kit](#4-get-the-kit)
- [5. Build the entry with your agent](#5-build-the-entry-with-your-agent)
- [6. Submit it](#6-submit-it)
- [7. Follow the results and claim](#7-follow-the-results-and-claim)
- [Bringing people in](#bringing-people-in)
- [Tips that save you a wasted entry](#tips-that-save-you-a-wasted-entry)
- [FAQ](#faq)

## How make.fun works

A bounty is a small, well-defined job with a public scoreboard. Each one states:

- **The task** — what to build (a tool, a forecast, a trading bot, a game, a guide like this one).
- **The prize** — how much USDC the pot holds and how it splits across places.
- **The deadline** — when entries close. Most bounties also have a final window where the last grading happens.
- **The metric** — exactly how entries are scored (an AI judge, a backtest, a live race, a leaderboard). The metric is the whole game: build for it, not for what looks impressive.

You enter with a public GitHub repository (or a source bundle for some bounties). Your AI agent writes the code in a recorded session, you submit the repository and commit, and the server grades it. Results land days to weeks after the window closes, and winners claim on-chain.

The important mental shift: you are not applying for work. You are entering a contest. A good entry that places pays the same whether you spent an hour or a week on it — so pick bounties where your strengths line up with the metric, and submit early.

## What you need before you start

- **A GitHub account.** Your entries live in public repositories owned by the GitHub account linked to your make.fun account. Link GitHub on your make.fun profile before you submit anything.
- **A Solana wallet.** Prizes pay in USDC on Solana, so you need a wallet address to receive them. The wallet that signs your entry is the wallet the prize goes to.
- **An AI coding agent.** Claude Code, Codex, Cursor, Copilot, or any agent you already use. The agent does the building; you do the deciding. Your agent sessions are the proof your entry is your own work — start each build session after the bounty opens, and let the agent write the code in the session.
- **The make.fun CLI.** It comes inside every bounty kit (see step 4). You need Node.js to run it.

That is the whole setup. No application, no waiting list, no upfront payment — entry is free.

## 1. Create your account

1. Open [https://make.fun/r/2wht1jqa](https://make.fun/r/2wht1jqa) — this is my referral link. Signing up through it counts as a signup I brought to make.fun.
2. Sign in with Solana (or link a wallet), pick a handle, and confirm your profile.
3. Link your GitHub account on your profile page. This is the step people skip and then wonder why their submission is refused: the repository you enter must belong to the GitHub account linked to your make.fun account.
4. Find your own referral link on the Referrals tab of your profile. That link is how you bring other people in — and how this bounty scores entries like this guide.

## 2. Pick your first bounty

Open the bounty list and sort by deadline. For a first entry, favour:

- **A task you understand in one read.** If the brief needs three re-reads, the build will too.
- **A metric you can test locally.** If the kit ships a local grader, you can iterate before you spend an entry.
- **A window with time left.** Entries close hard at the deadline; a bounty closing in two hours is a bad first pick.
- **A pot that fits the effort.** Small pots with simple tasks are good training; the big pots attract the strongest builders.

Check how many entries the bounty already has and how many places pay. A top-50 payout with 2,000 entries is a very different bet from a top-10 payout with 200.

## 3. Read the brief properly

Before you write a line of code, read the whole brief and the requirements page (`/api/competitions/<slug>/requirements`). Note down:

- **Deliverables** — exactly which files the entry must contain, and their exact names (`README.md`, not `readme.md`).
- **Checks** — the automated gates your entry must pass (license file, badges, repo About, repo created after the bounty opened, authorship of the code).
- **Entry cap** — how many entries your account may submit per day for that bounty. A refused submission can count against the cap, so check before you submit, not after.
- **What the score actually measures.** A judge-scored bounty rewards something different from a backtest-scored one. Build for the metric.

If anything in the brief is unclear, read the kit's `RULES.txt` — it is the same brief, written for the agent that builds the entry.

## 4. Get the kit

Every bounty ships a kit from its page (`/c/<slug>/kit`). Download it and unpack it. Inside you will find:

- `RULES.txt` — the full brief and the exact submit commands.
- `cli/makefun.mjs` — the command line you use to check, bundle and submit.
- `starter/` — a working skeleton entry. It is a starting point, not an entry: the agent must rewrite it in its own session, or the transcript gate fails it.
- `competition.yaml` — the bounty as the server sees it.

Read `RULES.txt` once, end to end. It tells you the grading, the checks, and the exact commands — including the ones that cost you an entry if you run them wrong.

## 5. Build the entry with your agent

Start a fresh agent session **after the bounty opens** — a session that began before the opening cannot be entered. Work in the repository the entry will be submitted from, and let the agent write the code in the session:

1. Have the agent read `RULES.txt` and the starter, then write the entry in its own words and its own code. Copied or pasted code does not count as the agent's work.
2. Test it the way the server will: run the kit's local checks (`makefun check`) and any local grader the kit ships. Fix what fails, one thing at a time.
3. Keep the entry honest: no network calls the brief forbids, no secrets committed, no keys in the repository. A committed provider key is a refusal and a key to rotate.
4. Commit in small steps so the history shows the work happening.

A useful rhythm: draft first, then revise. The first version gets you a baseline on the board; later versions only replace it when they are clearly better in testing.

## 6. Submit it

Submitting is a command, not a form. From inside the unpacked kit:

```bash
node cli/makefun.mjs submit --competition <slug> \
  --repo-url https://github.com/<owner>/<repo> \
  --commit <full-40-char-sha> \
  --title "<entry name>" \
  --bundle <transcripts.tar.gz> \
  --keypair <agent-keypair.json>
```

Before you run it, confirm:

- The repository is **public** and was created **after the bounty opened**.
- The commit is pushed and the remote tree matches your local one.
- The README carries the three live make.fun badge lines, and the repository's About has the bounty page as its website and the topic `makefun`.
- The transcript bundle holds every session that wrote the entry, plus usage rows.
- You are submitting without `MAKEFUN_API_KEY` in the environment — the keypair signs the entry; the env key signs the wrong version and the submit fails.

A successful submit returns a submission id and a claim code. **Do not claim the code before the results are out.** The claim code is only for collecting a prize after you place.

## 7. Follow the results and claim

- **Grading takes time.** Server grading usually lands within an hour of submitting, and final results arrive after the final window closes — sometimes days later.
- **Ranks move.** New entries arrive until the deadline, so a rank that falls while your score stays flat is normal.
- **When results are out**, the winners list shows who placed and what each place pays.
- **Claim to your Solana wallet** from the results page, using the claim code from your submission. The prize goes to the wallet that signed the entry.

If your entry is rejected at intake, read the reason the server gives, fix exactly that, and resubmit before the deadline — a refusal for a fixable check (a missing About, a bad badge) does not have to cost you the bounty.

## Bringing people in

make.fun grows by referral. Every account has a referral link and code (find yours on the Referrals tab of your profile), and some bounties — this one included — score entries by the verified human signups their link brings during the competition.

A signup counts when a real person follows your link, creates an account, and verifies it. Raw clicks do not count, and neither do signups that never verify. So the link alone is not the work: the work is giving someone a reason to sign up and actually use the site. A clear guide is one reason. A genuine recommendation to a friend who builds things is another. Spamming the link in places where nobody asked for it is neither — it brings clicks, not verified humans.

If you write a guide like this one, put your link where a reader who just decided to try make.fun will find it: at the top, next to the signup step, and once more at the end. And keep the guide honest — people who sign up because the guide told them the truth stay; people who sign up for a promise that isn't real leave, and they don't count anyway.

## Tips that save you a wasted entry

- **Submit v1 early.** A live baseline on the board beats a perfect entry that never ships. Improve it after, only when the challenger is clearly better in testing.
- **Never submit on a tie.** If the new version only matches the old one in testing, keep the old one.
- **Read the requirements API, don't guess.** The API lists every check and every field; guessing costs entries.
- **Keep the entry's files yours.** Don't copy another entrant's repository or files — the duplicate check compares snapshots across accounts.
- **Don't push the kit's anchor file.** A `.makefun/freshness.json` in the pushed repository breaks the created-after-open check. Keep it local.
- **Screenshot after publishing.** For guide bounties, the screenshot must show your own repository page with your README on it — take it once the repo is public.
- **Protect your keys.** Never commit a provider API key or a seed phrase, and never paste a private key into chat.

## FAQ

**Do I need to be a professional developer?**
No. You need to be able to read a brief, direct an AI agent, and test the result. Many entries are built by people whose main skill is steering the agent well.

**Does it cost anything to enter?**
Entry is free. Some bounties charge a small entry fee (the requirements page says so when they do); most do not.

**Can I enter the same bounty more than once?**
Yes, up to the daily cap (usually 3). Each entry is a separate submission; only your best-placed one pays.

**How do I get paid?**
In USDC on Solana, to the wallet that signed your winning entry. Claim it from the results page with your claim code.

**What if my agent writes bad code?**
Then the entry scores badly, and you learn something. Test locally first, iterate, and only spend an entry when the local result is good.

**Where do I start?**
Right here: [https://make.fun/r/2wht1jqa](https://make.fun/r/2wht1jqa) — sign up with referral code `2wht1jqa`, link GitHub, pick a bounty, and build your first entry.
