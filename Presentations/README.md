Presentations are hosted on GitHub Pages

* [Day 1 - Intro](https://lspiehler.github.io/Hands-On-Deep-Dive-with-X.509-and-Public-Key-Infrastructure/Presentations/Day-1-Intro.html)
  * [Asymmetric Cryptography](https://lspiehler.github.io/Hands-On-Deep-Dive-with-X.509-and-Public-Key-Infrastructure/Presentations/Day-1-A-Asymmetric_Cryptography.html)
  * [Hashing](https://lspiehler.github.io/Hands-On-Deep-Dive-with-X.509-and-Public-Key-Infrastructure/Presentations/Day-1-B-Hashing.html)

Alternatively, presentations can also be hosted locally. The following command can be used to host locally with Caddy 2:
```
caddy_windows_amd64.exe file-server --root "Presentations" --listen :81 --browse
```
Afterward, you should be able to browse to http://127.0.0.1:81/Day-1.html