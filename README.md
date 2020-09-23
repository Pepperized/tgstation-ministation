##ministation for /tg/station

The goal here is to make the lowpop (5-20 players) map MiniStation that was removed from tgstations code to work with modern BYOND.
I currently don't plan to bring the codebase up to date with tgstations main repo, and I have taken a lazy, destructive approach to 
incompatibilities (e.g. removing a feature that fails to compile). Many bugs are likely there, but it does work.

**Website:** http://www.tgstation13.org <BR>
**Code:** https://github.com/Pepperized/tgstation-ministation <BR>
**Based On:** https://github.com/tgstation/tgstation <BR>
**Wiki** http://tgstation13.org/wiki/Main_Page <BR>


##DOWNLOADING

There are a number of ways to download the source code. Some are described here, an alternative all-inclusive guide is also located at http://www.tgstation13.org/wiki/Downloading_the_source_code

Option 1:
Follow this: http://www.tgstation13.org/wiki/Setting_up_git

Option 2:
Install GitHub::windows from http://windows.github.com/
It handles most of the setup and configuraton of Git for you.
Then you simply search for the tgstation repository and click the big clone
button.

Option 3: Download the source code as a zip by clicking the ZIP button in the
code tab of https://github.com/tgstation/tgstation
(note: this will use a lot of bandwidth if you wish to update and is a lot of
hassle if you want to make any changes at all, so it's not recommended.)

##INSTALLATION

First-time installation should be fairly straightforward.  First, you'll need
BYOND installed.  You can get it from http://www.byond.com/.  Once you've done
that, extract the game files to wherever you want to keep them.  This is a
sourcecode-only release, so the next step is to compile the server files.
Open tgstation.dme by double-clicking it, open the Build menu, and click
compile.  This'll take a little while, and if everything's done right you'll get
a message like this:

```
saving tgstation.dmb (DEBUG mode)
tgstation.dmb - 0 errors, 0 warnings
```

Once that's done, open up the config folder.  You'll want to edit config.txt to
set the probabilities for different gamemodes in Secret and to set your server
location so that all your players don't get disconnected at the end of each
round.  It's recommended you don't turn on the gamemodes with probability 0,
except Extended, as they have various issues and aren't currently being tested,
so they may have unknown and bizarre bugs.  Extended is essentially no mode, and
isn't in the Secret rotation by default as it's just not very fun.

You'll also want to edit config/admins.txt to remove the default admins and add
your own.  "Game Master" is the highest level of access, and probably the one
you'll want to use for now.  You can set up your own ranks and find out more in
config/admin_ranks.txt

The format is

```
byondkey = Rank
```

where the admin rank must be properly capitalised.

Finally, to start the server, run Dream Daemon and enter the path to your
compiled tgstation.dmb file.  Make sure to set the port to the one you
specified in the config.txt, and set the Security box to 'Safe'.  Then press GO
and the server should start up and be ready to join. It is also recommended that
you set up the SQL backend (see below).

##MAPS

/tg/station currently comes equipped with seven maps.

* [MiniStation](http://tgstation13.org/wiki/MiniStation)

Although maps other than MiniStation exist in this repo, the purpose of the repo is to maintain MiniStation as best as possible.

##SQL SETUP

The SQL backend requires a MySQL server. SQL is required for the library, stats tracking, admin notes, and job-only bans, among other features, mostly related to server administration. Your server details go in /config/dbconfig.txt, and the SQL schema is in /SQL/tgstation_schema.sql and /SQL/tgstation_schema_prefix.sql depending on if you want table prefixes.  More detailed setup instructions are located here: http://www.tgstation13.org/wiki/Downloading_the_source_code#Setting_up_the_database

##IRC BOT SETUP

Included in the repository is a python3 compatible IRC bot capable of relaying adminhelps to a specified
IRC channel/server, see the /bot folder for more

##LICENSE

As this repo is forked from tgstation, the following license information applies:

All code after commit 333c566b88108de218d882840e61928a9b759d8f on 2014/31/12 at 4:38 PM PST (https://github.com/tgstation/tgstation/commit/333c566b88108de218d882840e61928a9b759d8f) is licensed under GNU AGPL v3 (http://www.gnu.org/licenses/agpl-3.0.html).

All code before commit 333c566b88108de218d882840e61928a9b759d8f on 2014/31/12 at 4:38 PM PST (https://github.com/tgstation/tgstation/commit/333c566b88108de218d882840e61928a9b759d8f) is licensed under GNU GPL v3 (https://www.gnu.org/licenses/gpl-3.0.html).
(Including tools unless their readme specifies otherwise.)

See LICENSE-AGPLv3.txt and LICENSE-GPLv3.txt for more details.

tgui clientside is licensed as a subproject under the MIT license.
Font Awesome font files, used by tgui, are licensed under the SIL Open Font License v1.1
tgui assets are licensed under a Creative Commons Attribution-ShareAlike 4.0 International License
(http://creativecommons.org/licenses/by-sa/4.0/).

See tgui/LICENSE.md for the MIT license.
See tgui/assets/fonts/SIL-OFL-1.1-LICENSE.md for the SIL Open Font License.

All assets including icons and sound are under a Creative Commons 3.0 BY-SA
license (http://creativecommons.org/licenses/by-sa/3.0/) unless otherwise indicated.
