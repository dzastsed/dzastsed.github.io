---
layout: post
categories: stories-guides
---
## Table of contents:
- [Backstory](#backstory)
- [A new hope?](#a-new-hope)
- [Another problem](#another-problem)
- [Conclusion](#conclusion)

*If you want to skip the story, just jump to [Conclusion](#conclusion)*.
## [Backstory](#backstory)
Back in late 2024 I obtained a Steam Deck, and first thing I wanted to do with it after coming back to my university dorm was connecting to Eduroam. Of course I know its terrible nature and horror stories about from the internet, some of which I already experienced myself, but tried anyway (I was successfully able to use it with Ubuntu based distros). Well, what do you know, I could not connect to it, just like with Arch linux I tried back in 2023. This time I was determined to once and for all to figure out the solution.

After a LOT of research, results were fruitless. Many attempts were done - dumping network certificate with other distro, trying to modify cat.eduroam.org login script to match my university's (mine does not have support for it :\)\)\) asked our IT admin to add support but they basically told me to gtfo, go figure), using university's official guide (which is almost 10 years old), but nothing worked. Then, I asked the best resource on the internet - reddit.
## [A new hope?](#a-new-hope)
Surprisingly, I got a suggestion to try something I didn't see in other troubleshooting threads:
![steamdeck_1](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/steam_deck/post.png?raw=true)

It turned out that SteamOS (and Arch and probably many of its derivatives?) uses `iwd` instead of `wpa-supplicant` as default Wi-Fi backend.
So I immediately tried this. I first did it the dumb way - switched via terminal using guides from Arch wiki. Turns out there's an easier way! Just enable Developer settings and switch it in developer options:

![steamdeck_2](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/steam_deck/switch.jpg?raw=true)
## [Another problem](#another-problem)
Welp, turns out this did not help either. It would progress further in connecting, but would still stop and ask for my password. So what's the issue here?

Looking at `wpa-supplicant` logs, it seems that there is some sort of SSL protocol issue:
![steamdeck_3](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/steam_deck/logs.jpg?raw=true)

So how do we fix this?

Thankfully, [Arch wiki](https://wiki.archlinux.org/title/Wpa_supplicant#Problems_with_Eduroam) is a brilliant resource, and there is a section made specifically for this issue. [This](https://wiki.archlinux.org/title/NetworkManager#WPA_Enterprise_connections_fail_to_authenticate_with_OpenSSL_%22unsupported_protocol%22_error) section is the exact fix you need, if you encounter protocol error.

After running the command `nmcli connection modify 'eduroam' 802-1x.phase1-auth-flags 32` and restarting the service with `sudo systemctl restart NetworkManager` I got my Steam Deck successfully connecting to eduroam.

![steamdeck_4](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/steam_deck/success.jpg?raw=true)

## [Conclusion](#conclusion)
So, to sum up, what is required to connect to eduroam?
 - You need some basic knowledge of terminal usage, and root password set up for your Steam Deck (plenty of guides online).
 - Do the initial connection attempt via desktop mode, gaming mode will not work no matter what.
 - You need to switch network backend from `iwd` to `wpa-supplicant` (see [here](#a-new-hope)).
 - If it still refuses to connect, you need to modify `NetworkManager` config (see [here](#another-problem)).

Huge thanks to MinimumHistorical359 on reddit for pushing me towards the right direction!
