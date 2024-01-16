# Reporting bad behavior on the Fediverse

## what
Reporting is the main method to bring bad behavior to Mastodon instance admins.


## the steps, in brief
* A member, Gallant, reports nasty behavior from another Mastodon user, Goofus
* Gallant's instance's admin can take action against Goofus, or Goofus's instance
* Goofus's instance's admin can take action against Goofus
* the admins can chat

## who? the cast
Gallant is reporting Goofus's behavior.

[Paraphrasing from Wikipedia](https://en.wikipedia.org/wiki/Goofus_and_Gallant):
Goofus and Gallant is a comic strip from Highlights for Children.
Gallant's actions are right and good, virtuous and respectful.
Goofus's actions are wrong and bad, rude and selfish.

This is an attempt to keep it light.

## reporting bad behavior
### for Gallant: how to report
There are menus that let you report bad behavior from posts and profiles.

1. First, the context menu looks like triple dots, vertical (&vellip;) or horizontal (&mldr;).
The specific option is "Report @Username".

2. Choose the best reason for reporting it:
* I don't like it
* It's spam
* It violates server rules -
  this will list the Server Rules on your server for selection; they vary by server
* It's something else

3. You can select specific posts you want to draw attention to, to demonstrate why you're reporting

4. "Is there anything else you think we should know?"
There's a free-form text field here, where you can go into more detail.

There's also an option to send the report to the home instance of the post or member.
The default is "send".

If you're not familiar with the instance in question, you can skip sending it.

### anonymity
Gallant's admin can see that Gallant made the report; Goofus and Goofus's admin can only see the reporting instance.


## For Gallant's admin, on the reporting instance
Access is in the Admin interface, under Moderation / Reports.

Asking for clarification from Gallant can be helpful; one can do that with a ~~DM~~ Mentioned-only post.

The admin can Limit or Suspend that profile (Goofus), and leave notes on the actions taken, for their future self and for other admins.
I *think* suspending that profile will remove various debris - follows, spammy DMs, etc.

Separately, Gallant's admin can investigate Goofus' instance - 
* Goofus *is* the admin for that instance?
* their `/about` page is offensive?
* they've got a bot tracking and announcing who's blocking them?

These are bad signs.
The admin can opt to Silence or Suspend Goofus's instance.

### news from Goofus's server
From the admin UI, it's possible to see whether profiles were suspended remotely.
Or, going directly to their account on the remote server gives you a "access denied" page - "You don't have permission to view this page".

### news for Gallant
It's not automatic to let the reporter - Gallant - know if any action was taken, on or from either relevant instance.
It seems appreciated, though.
I like to post "heads up, the mastodon.social spammer you reported has been suspended both here and on their home instance."


## For Goofus's admin, on the reported instance
Weigh whether what Goofus said broke the local Server Rules.

Options from the Admin Interface:
* Warn
* Freeze -
This makes the account read-only.
* Force-sensitive -
This is for all posts.
* Limit / Silence -
Hides the account from local users.
* Suspend -
Effectively deletes the account.
* Turn into memoriam -
This is an odd place for it, but ok.

If it's someone spamming at volume, deleting the profile without warning makes sense.

Goofus isn't automatically notified of the report.
Even without action taken, it's probably good to let the reported member - Goofus - know that, heads up, someone reported you for _this reason_.


## further admin conversations
It looks like going to the `/about` page, getting the admin address, and starting a ~~DM~~ Mentioned-only visibility conversation is best.


## why not use admin-to-admin conversations?
* There are over 10k Mastodon instances.
Relying on admin-to-admin conversation wouldn't scale *that* well.
* That relies on Gallant's admin, and Goofus's admin, to react to the messages.
* It would be harder to keep track of.
* How would reporting DMs work?


## not covered yet
This is a rough draft.

I tried to document what I had access to; I'm admin on a Hometown instance, which is currently a fork of Mastodon v4.0.

Starting with Mastodon v4.2, reports are sent more broadly.
In addition to Goofus's and Gallant's admins, the admins of other people in the reported posts (conversations?) will be notified.

This doc covers Mastodon and its forks, like Hometown.
Other Fediverse software, like Firefish, behaves differently:
* reports only go to Gallant's admin, and they have to decide whether to pass it on to Goofus's admin.

There's probably more; let me know.
