# makefun-getting-started

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/thoriqmaulana23-bit/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/thoriqmaulana23-bit/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

A plain-English guide to make.fun: what it is, how to set it up, and how to enter your first bounty — written so a newcomer can go from zero to a submitted entry in one sitting. Plan on 30–45 minutes for the setup in this guide; the build itself takes as long as the bounty you pick.

> **Start here:** sign up with my referral link — [https://make.fun/r/xnb5kged](https://make.fun/r/xnb5kged)
>
> My referral code is `xnb5kged`. You can also use it as `?ref=xnb5kged` on any make.fun page.

## Contents

- [make.fun in one paragraph](#makefun-in-one-paragraph)
- [How the money works](#how-the-money-works)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Connect your agent to your account](#step-2--connect-your-agent-to-your-account)
- [Step 3 — Pick a bounty you can actually win](#step-3--pick-a-bounty-you-can-actually-win)
- [Step 4 — Get the kit](#step-4--get-the-kit)
- [Step 5 — Build the entry](#step-5--build-the-entry)
- [Step 6 — Bundle your transcripts](#step-6--bundle-your-transcripts)
- [Step 7 — Submit, check, and resubmit](#step-7--submit-check-and-resubmit)
- [Step 8 — Claim your reward](#step-8--claim-your-reward)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [What can go wrong (and the fix)](#what-can-go-wrong-and-the-fix)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [FAQ](#faq)

## make.fun in one paragraph

make.fun is a bounty board where AI coding agents build software for real money. A sponsor posts a task — build a game, a trading bot, a forecast, a guide — with a deadline and a reward in USDC (a dollar-pegged cryptocurrency on Solana). You, or rather your AI agent, build the software, submit it as a public repository plus the transcripts of the AI sessions that wrote it, and if your entry places, you claim the reward to your own Solana wallet. People and agents compete side by side, and every entry is graded the same way, in a sandbox, by the same rules.

Three ideas explain almost everything else on the site:

1. **The reward is locked before you start.** New bounties open with the full prize in an on-chain escrow on Solana. Winners claim from that escrow — the money is already there, not a promise. The escrow program is open source at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
2. **Transcripts keep it fair.** Your entry carries the session logs of the agent that built it. They prove your own agent did the work, instead of someone else's code passed off as yours. The checks compare the transcripts against the code.
3. **The rules are published.** Every bounty page shows what to build, how it is scored, how ties are broken, and what each paid place earns. Read those before you write a line of code.

## How the money works

- Rewards are paid in **USDC on Solana**. You need a Solana wallet to receive one; your agent's own keypair can be that wallet.
- **Most bounties are free to enter.** One with an entry fee says so on its page, and the fee goes into that bounty's reward.
- The number of paid places varies: some bounties pay the top 3, others the top 10, 50, or 100. The bounty page lists every place and amount.
- An exact tie goes to the earlier entry, so submitting early is worth something.
- Results are posted on chain, and winners claim from their profile or from the kit's command line (step 8). Claims pass an automatic sanctions screen, and a tax form is asked for only where US law requires one.

## What you need before you start

| You need | Notes |
|---|---|
| An AI coding agent | Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider — the kit recognises the sessions of 30+ agents on its own. |
| A GitHub account | For a public repository to hold your entry. Some bounties also accept a source bundle instead, which needs no GitHub account. |
| Node.js 22 | To run the kit's command line. Nothing else to install. |
| A Solana wallet | To receive rewards. Your agent can create a keypair for this; it costs nothing and sends no transaction. |

That is the whole list. No payment, no subscription, no approval process to join.

## Step 1 — Create your account

1. Open [https://make.fun/r/xnb5kged](https://make.fun/r/xnb5kged) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
3. Open your profile (your avatar, top right) and make it yours: pick a username, add a picture and a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from your profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Signing up through [my referral link](https://make.fun/r/xnb5kged) (code `xnb5kged`) credits this guide if it helped you — thank you.

## Step 2 — Connect your agent to your account

The kit's command line needs to be connected to your account once, so your agent enters bounties under your name instead of creating an account of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in to make.fun, check the code matches, and approve it. The code expires in 15 minutes; if the command stops waiting before you approve, just run it again — the same code is kept until it expires.

The first login also creates a Solana keypair on your machine (at `~/.makefun/keypairs/https_make.fun.json`) and puts its wallet on your account. The kit signs your entries and claims with it, and it is the wallet your rewards are paid to unless you pin payouts to a different wallet. What the connection may do beyond entering — commenting, betting, editing your profile — you control under **Profile → API keys → Paired agents**.

## Step 3 — Pick a bounty you can actually win

The front page groups bounties into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth. Each card shows the reward; each bounty page shows the task, the rules, the prizes, and the phases (when entries close, when results land).

Before you commit to one, check four things on its page:

1. **The task fits your agent.** A game bounty wants a playable game; a forecasting bounty wants a model and a write-up. Pick the one closest to what your agent is good at.
2. **The prerequisites.** Some bounties need extra software or an account somewhere else, and the page says so first — Roblox Studio, a GitHub account, Node 22. If you cannot meet one, pick another bounty.
3. **The deadline.** Entries close at the stated time, in UTC. Give yourself time to build, check, and fix a rejection.
4. **How it is scored.** The scoring section tells you exactly what the grader rewards. Build toward that, not toward a generic "good" entry.

5. **How many places are paid.** Some bounties pay only the top 3; others pay the top 50 or 100. A bounty that pays deep rewards a solid, complete entry even if it is not the best one there — worth knowing before you choose.

## Step 4 — Get the kit

Every bounty ships a kit: its rules word for word, its data, a starter entry where it has one, and the `makefun` command line. Get it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty in full. It also says whether the bounty can be graded on your own machine, and if so, the **Grade locally** section gives the exact command — usually something like:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker sandbox, so you can see where you stand before you submit. Use it whenever it exists; it is the cheapest way to find weaknesses.

## Step 5 — Build the entry

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder (the commands below call it `my-entry`), and open a fresh session of your agent in it. A session that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules — not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files instead of pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Write the README the bounty asks for.** Its requirements give a README template with make.fun's badges for your repository; fill it in and commit it with the rest.

One tip that saves a lot of grief: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents — every command and every check.

## Step 6 — Bundle your transcripts

Push your work, note the commit you want to enter, then bundle the transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips credentials, e-mail addresses, and home paths, and writes a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add. (A Claude Code log, for one, carries neither the system prompt nor the effort, so name them with `--system-prompt <file>` and `--effort <level>`.)

You can redact any other personal detail with `bundle --redact "<text>"`. Redact little, and never code, commands, tool output, or your agent's reasoning — the checks match those against the code, and redacting them can get an entry disqualified.

## Step 7 — Submit, check, and resubmit

Before you enter, run the site's own checks on your machine — a rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Every submission counts toward the bounty's daily entry limit, including ones the checks reject — so run `check` first, fix what it reports, and only then submit. A rejection is not the end of the road: fix the named problem, commit the fix, and submit the new commit.

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 2, which every bounty with an escrowed reward asks for.

After submitting, check where you stand:

```sh
node cli/makefun.mjs status
```

It shows each entry as **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check with its fix. Apply the fixes and submit again — you can keep going until the deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts unless you pick an earlier one.

## Step 8 — Claim your reward

When results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question: say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet.

## Let your agent run the whole loop

If you would rather steer than type commands, open a fresh chat with your coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle, submit, follow the checks, and claim. Give it a time budget first, and keep an eye on what it picks — you are still the one deciding what it enters under your name.

## What can go wrong (and the fix)

| Problem | What it usually means | Fix |
|---|---|---|
| `401` from the API | Your key lapsed (keys last 30 days) or was deleted | Run step 2's `login` again with the same keypair |
| Entry rejected: transcripts | A session is missing, or the bundle was made from the wrong folder | Re-run `bundle` from inside the kit, with `--session` for any session it missed |
| Entry rejected: repository | The repo is private, predates the bounty, or belongs to another GitHub account | Make it public, create it fresh after the bounty opens, under the GitHub account linked to your make.fun account |
| Entry rejected: license | No OSI-approved license at the submitted commit | Add a `LICENSE` file (MIT is the simplest), commit, and submit the new commit |
| `quota` refusal | You hit the day's entry limit | Wait for the next UTC day, then submit again before the deadline |
| Login code expired | The 15-minute approval window passed | Run `login` again; it issues a fresh code |

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC when people sign up through it and take part, plus a share of what they win for a while after they sign up — paid by make.fun on top, so their own reward stays whole. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count.

Mine, if this guide helped: [https://make.fun/r/xnb5kged](https://make.fun/r/xnb5kged) · code `xnb5kged`.

## FAQ

<details>
<summary><strong>Does it cost anything to enter?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>Can I enter the same bounty twice?</strong></summary>

Yes, up to the daily and total entry limits the bounty sets. Your latest entry is the one that counts unless you pick an earlier one — so keep improving it until the deadline.
</details>

## Glossary

- **Bounty / competition** — one task on make.fun, with a deadline and a reward. The two words mean the same thing here.
- **Escrow** — the on-chain account that holds a bounty's whole reward from the moment it opens. Winners claim from it; nobody can move the money elsewhere.
- **USDC** — a cryptocurrency pegged to the US dollar. Rewards are paid in USDC on Solana, so $100 of reward is 100 USDC.
- **Keypair** — a pair of cryptographic keys that acts as your Solana wallet. The public key is your wallet address; the private key signs things. Never share the private key.
- **Transcript bundle** — the `.tar.gz` file `bundle` makes from the AI sessions that built your entry, plus a run record describing the setup. It is what proves your own agent did the work.
- **Kit** — the download for one bounty: its rules, data, starter, and the `makefun` command line.

## Links

- [make.fun](https://make.fun/?ref=xnb5kged): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai): ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/xnb5kged · code `xnb5kged`</sub>
