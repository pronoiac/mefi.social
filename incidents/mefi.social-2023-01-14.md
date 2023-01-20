# incident, 2023-01-14, mefi.social

## times
> these times are UTC; Pacific is 8 hours later.

125am UTC / 525pm Pacific, Pronoiac, noted the website was nonresponsive after getting an error from Ivory, trying to load the parent of a reply.
The hosting dashboard doesn't reflect any activity or status issues.
(This is *not* to upgrade Hometown, which had a security / privacy patch release about 24 hours ago.)

130am, wrote a ticket requesting help from hosting.
I tried accessing the Local Timeline from Toot!, without success.

135am, unlike [last time,](mefi.social-2022-12-28.md) I'm unable to load the Sidekiq dashboard.

140am, I'm polishing up the previous incident report.

150am, only getting server errors.
On the previous incident, forcing a deploy over a minor setting nudged Sidekiq back into responding.
Let's try that again!

200am, clicking "Deploy Instance" from a different browser, in case Firefox somehow wasn't communicating.
Attempting wget, it's geting 504 Gateway Time-out.

245am, check ipv4 vs ipv6?
```
$ curl -v --ipv4 https://mefi.social
[error after 35sec or 60sec]
$ curl -v --ipv6 https://mefi.social
[error after 60sec]
```

255am, posting this WIP note.

518am, reverted minimal change (unused LibreTranslate endpoint).
Attempting deployment, to no avail.

715am, made an alt account on hachyderm, and DM'ed myself, so I get notified of when the server returns.

745am, got notified of the message.
It looks like we're good to go!
I kept an eye on it for an hour, and forgot to update the (new) status page.


## action items
* consider add-ons from hosting
  * High Availability (19.00€/month)
  * Premium Support (33.00€/month)
* [Investigate monitoring](https://github.com/pronoiac/mefi.social/issues/33)
* set up a status page - [done!](https://status.mefi.social/)
* chill out and wait for hosting, I guess?
They responded:
  * a single app server lost connectivity. i am not sure why; but a reboot got it fully operational again.
  * 'high availability' option would have given you a secondary app server which would have kept your instance online, if only at slightly degraded performance.