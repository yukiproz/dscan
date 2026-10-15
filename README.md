# ❄ dscan

a disk scanner. fast, no small talk, powered by gdu-go.

a wanderer must know the terrain.

## install

needs [gdu-go](https://github.com/dundee/gdu) in PATH.

```sh
git clone https://github.com/yukiproz/dscan.git
cd dscan && chmod +x dscan
sudo ln -s "$PWD/dscan" /usr/local/bin/dscan
```

## use

```sh
dscan                  # disk overview + $HOME breakdown, depth 1
dscan /some/path       # breakdown of a path, depth 2
dscan /some/path 3     # breakdown of a path, depth 3
dscan --remote 'ssh mymachine' /var/log   # scan a distant machine over ssh
```

## one trap

never pipe human-friendly gdu-go output into `sort -rn` — it ranks
`933 MiB` above `11 GiB`. use `--no-prefix` (raw bytes) when sorting,
or just read the units carefully.

*❄ snow never explains itself.*
