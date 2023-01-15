# incident, 2022-12-28, mefi.social

## summary
sidekiq, which delivers messages, internally and externally, got stuck.
The timelines (both local and federated) stopped updating, local posts weren't visible elsewhere, local @'s weren't notified.
Restarting sidekiq got everything back on track. 

## timeline
> these times are UTC; Pacific is 8 hours later.

2022-12-27, unclear time- Sidekiq wedged.

00:29- [Rodneylives noticed that timelines were stalled and @'ed pronoiac](https://mefi.social/@rodneylives/109588469731235462); due to the nature of the issue, notifications didn't happen.

01:14 - I (Pronoiac) stumbled on stalled timelines, checked the local timeline, saw RL's message, noticed sidekiq had stalled, pinged support, and made a public reply.

Several hours passed; the issue persisted. I watched mysteries with friends, and had a nap.
I went looking for sidekiq buttons.

08:11 - On the hosting side, I changed an irrelevant minor setting, and deployed the server.
After a few minutes, sidekiq kicked into gear. 

08:45- the queue was at 31k items.
I watched the "queued" number go up a bit, and eventually drop, slowly then quickly. 

09:12- I got notifications, for much earlier conversations. 

09:20- the sidekiq queue is under half of its peak.

09:33- the sidekiq queue backlog was cleared.

## to do
* reach out to hosting: who should monitor? Or fix? What happened?
  * this shouldn't happen
  * deploying should fix it
  * ours was the only impacted instance
  * if it recurs, contact them, they can investigate the cause
* set up encryption, for backups, in case I don't like their answers
* Work out hosting's support hours
* go through mastodon sidekiq settings, look for alternate routes for this, and document them
  * in /sidekiq/busy:
    * stats
    * Quiet all - stop picking up new queue items, prepare to drain
    * Stop - save in-flight items to disk and shutdown
* having other people back me up, re: administration, moderation, etc. I haven't documented this yet.
* post alternate contact methods?
* Investigate monitoring - [I brainstormed a heartbeat monitor](https://github.com/pronoiac/mefi.social/issues/33)
* ping Hometown maintainer:
  * is this of interest?
  * is there anything we should do next time for diagnosis?

