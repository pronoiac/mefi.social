# migrating mastodon accounts

## what
This is about *how* to migrate an account between instances.
Not about the etiquette of having multiple accounts.

This covers transferring:
* bookmarks
* mutes
* blocks
* follows
* followers, mostly

Not covered:
* posts
* favorites
* DMs

### set up the new account
On the new server:
Make an account.

Manually create or copy:
* bio
* profile pic
* banner

### leave notes
On the new server:
Post that you're moving from your old account.

On the old server:
Perhaps post and pin something like: "I'm transferring to my new account, @new@example.com"
Mentioning and linking the new account from the bio can be helpful.

These can be helpful for:
* locked accounts, who have to approve follow requests
* federation software that doesn't handle account migration automatically, like Pleroma
* people updating their custom lists
* a fallback, sometimes the automatic measures fail

### copy your settings
I wrote this about Follows, but it's also useful for:
* blocks, both accounts and domains
* mutes
* bookmarks

Old server:
Export your follows:
Import and export / Follows, CSV.

New server:
Import your follows:
Import and export / Import.

### transferring
On the new server:
Set up an alias.
It's within Settings / Account / Moving *from* a different account.

#### moving vs redirection
With this step, you could lose access to your old account.
You won't be able to edit the old profile, or make, edit, or delete posts.
Handle or save notifications, DMs, etc.

There's a choice to make.
Either one has a few notes on their page.
This is a rough attempt to summarize.

For the reversible Redirection / "Account migration":
* Your current account's profile will be updated with a redirect notice and be excluded from searches
* No other data will be moved automatically
* Your current account will not be fully usable afterwards. However, you will have access to data export as well as re-activation.

"Move *to* a different account" has all the above, and also:
* This action will move all followers [best effort] from the current account to the new account
* The new account must first be configured to back-reference [the old account]
* After moving there is a waiting period (aka "cooldown period", usually 30 days?) during which you will not be able to move again

On the old server:
Redirect or move to the new account.
It's within Settings / Account / Move to a different account.

### troubleshooting
Reportedly, it can take up to a week to process a migration.

Your old instance, your new instance, and your followers' instances all play roles:
* any of them being slow, slows everything down
* mutes, blocks, defederation between instances can be roadblocks

Redoing the migration later - after the 30 day cooldown period? - could help with stragglers.
* that might look like setting the "move *to"* again - is that an option? - or like asking your old instance / hosting to run a `tootctl accounts migrate [username]`


## references
* [joinmastodon docs on moving](https://docs.joinmastodon.org/user/moving/)
* [@feditips@mstdn.social post](https://mstdn.social/@feditips/107939441820299376)
* [Coding It Wrong >> Migrating a Mastodon Account](https://codingitwrong.com/2022/10/10/migrating-a-mastodon-account.html)
* [Julia Evans, on troubleshooting migration](https://social.jvns.ca/@b0rk/109702593487773525)
* [@adamcr, on last-minute edits](https://mastodon.lol/@adamcr/109837226707470902)
