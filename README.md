# ❄ dscan

Fast disk analysis using **gdu-go** in non-interactive mode.

`du` walks the whole tree slowly — gdu-go gives the same answer dramatically
faster. This script is the wrapper I reach for first whenever disk space
questions come up.

## install

Needs [gdu-go](https://github.com/dundee/gdu) on PATH.

```sh
git clone https://github.com/yukiproz/dscan.git
cd dscan && chmod +x dscan
sudo ln -s "$PWD/dscan" /usr/local/bin/dscan
```

## usage

```sh
dscan                  # disks overview + top-level breakdown of $HOME
dscan /some/path       # breakdown of path (depth 2)
dscan /some/path 3     # breakdown of path (depth 3)
dscan --remote 'ssh myhost' /var/log   # scan a remote host over ssh
```

## the one gotcha

Never pipe human-readable gdu-go output through `sort -rn` — it ranks
`933 MiB` above `11 GiB`. Use `--no-prefix` (raw bytes) when sorting,
or just read the units carefully.

*Built with ❄ by yuki*
