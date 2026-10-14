# thrivari-watch

Thrivari's outside watcher. Every 10 minutes GitHub Actions checks that Thrivari's servers answer, from outside
Cloudflare and Google, so an outage that also takes down our own alerts still gets noticed. A failed run means
something was down; GitHub emails the owner about it.

What it checks: `https://api.thrivari.com/health` (database, scheduled job, alert email), the PRVSN dash, the PRVSN
booking page, and thrivari.com. Nothing here is secret: these are public addresses.
