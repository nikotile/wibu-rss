# wibu-rss
⚠ The regex used to parse HTML content may break if the site owners decided to radically change their content layout for some reason. If it happens, let me know.

⚠ July 2022 - Kanau went offline since last month. No futher news from them.

Generates RSS feeds from the following Indonesian otaku/weeb news sites:
- www.risamedia.com
- kanau.org
- mediaformasi.com, they have their own RSS feed. Well, this doesn't hurt.
- tirto.id, not actually an otaku site, but hope it's helpful.

If you just want to consoom the feeds, you can get them [here](https://nikotile.xyz/library).

## Tools
- `shup`, a POSIX HTML parser ([here](https://github.com/pystardust/shup))
- `curl`
- `sed`, `grep`, `awk`
- and other tools from the GNU Core Utilities.

## Usage
The entry point is `./generate` which will source files/functions inside the `src` folder. Outputs are in the `feeds` folder (will be created by the script if doesn't exist).

Notes:
- Since each site has different structures (wacky HTML + JavaScript), each will have their unique file/function.
- The actual xml file isn't reverse chronological, but most RSS readers are smart enough to sort them reverse chronologically.

Before running a cronjob:
- Make sure to tell cron the path to `shup`, e.g. by defining `PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`, or wherever `shup` is installed, in the crontab.
- Customize/edit the `dir` variable in `generate` to make the directory absolute.
