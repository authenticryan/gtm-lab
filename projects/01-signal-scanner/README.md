# 01 · Signal scanner

Watches a list of companies for signals and turns each new one into a task in a CRM (Attio), so I act on timing instead of checking websites by hand.

**Status:** Briefing. The brief is below. Code comes next.

## Brief

*I write this part. Answer each in two or three lines.*

**Problem.** What breaks today without this? What does acting late cost?

**Who it's for.** Me first. Who else would run this? (A founder watching competitors? An SDR watching accounts?)

**Signals.** Which three signals are worth a task, and which are noise? Start with:
- New job posting (which roles count?)
- Funding or launch news
- One more you pick

**Metric.** How will I know it works? (Signals caught per week, false positives, time from signal to task.)

**What I'll learn.** Which skills from [TRACK.md](../../TRACK.md) this proves.

**Out of scope.** What it won't do in v1.

## Coach notes

**What this project teaches:** calling public APIs, deduplicating events, running code on a schedule without you, and writing to a CRM through its API. Those are the core of Station 1.

**Free building blocks to look at:**
- Many companies post jobs on Greenhouse, Lever or Ashby, which publish public JSON job boards. Check which one each of your companies uses.
- News via RSS feeds.
- GitHub Actions on a cron schedule to run it daily for free.
- Attio's REST API to create tasks. The key goes in `.env` locally and in a GitHub secret for Actions.

**The part you write first:** the dedupe logic. Given yesterday's postings and today's, what counts as new? I'll review your version before we build around it.

**Exit check:** a new posting on a watched job board becomes an Attio task within 24 hours, without duplicates, on a schedule you don't touch.

**Privacy:** the company list lives in `companies.yaml`, which is gitignored. Commit `companies.example.yaml` with sample companies instead.
