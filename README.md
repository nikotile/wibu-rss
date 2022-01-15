# wibu-rss
Generates RSS feeds from the following Indonesian otaku/weeb news sites:
- kanau.org
- mediaformasi.com
- www.risamedia.com

If you just want to consoom the feeds, you can get them [here](https://nikotile.xyz/library).

## Tools
- `shup`, a POSIX HTML parser ([here](https://github.com/pystardust/shup))
- `curl`
- `sed`, `grep`, `awk`, and other tools from the GNU Core Utilities.

## Usage
The entry point is `./generate` which will source files/functions inside the `src` folder. Outputs are in the `feeds` folder (will be created by the script if doesn't exist).

Note:
- Since each site has different structures (wacky HTML + JavaScript), each will have their unique file/function.
- The actual xml file isn't reverse chronological, but most RSS readers are smart enough to sort them reverse chronologically.
