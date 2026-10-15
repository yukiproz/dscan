# ❄ dscan

pemindai disk. cepat, tanpa basa-basi, memakai gdu-go.

pengembara harus tahu medannya.

## pasang

butuh [gdu-go](https://github.com/dundee/gdu) di PATH.

```sh
git clone https://github.com/yukiproz/dscan.git
cd dscan && chmod +x dscan
sudo ln -s "$PWD/dscan" /usr/local/bin/dscan
```

## pakai

```sh
dscan                  # ringkasan disk + bedah $HOME sedalam 1 tingkat
dscan /suatu/path      # bedah path sedalam 2 tingkat
dscan /suatu/path 3    # bedah path sedalam 3 tingkat
dscan --remote 'ssh mesinku' /var/log   # memindai mesin jauh lewat ssh
```

## satu jebakan

jangan pernah menyalurkan output gdu-go yang ramah-manusia ke `sort -rn` —
ia menempatkan `933 MiB` di atas `11 GiB`. pakai `--no-prefix` (byte mentah)
kalau perlu mengurutkan, atau baca saja satuannya baik-baik.

*❄ salju tidak pernah menjelaskan dirinya.*
