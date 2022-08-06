### IPTV MALAYSIA (only in MALAYSIA)
File m3u | Short Link | Remarks
------------ | ------------- | -------------
Livetvvodje.m3u | https://bit.ly/39pH77g
njoi.m3u | https://bit.ly/38OmjDA
tv.m3u | https://tinyurl.com/myfreeviewlist
tvmuar7.m3u | https://bit.ly/tvmuar7

Playlist m3u can be used on :
* [Tivimate](https://play.google.com/store/apps/details?id=ar.tvplayer.tv)
* [OTT Navigator](https://ott-nav.com/)
* [IPTVnator IPTV](https://github.com/4gray/iptvnator#readme) for PC Windows

# Media Prima DailyMotion PHP
Retrieve Media Prima HLS manifest from Dailymotion.

## Info

1. ~~Media Prima locked this video as private , so the metadata trick won't work.~~

**(UPDATE : Dailymotion changed the method to get the manifest URL for private video , last time it was under directly the embed video page , but now they will request with the metadata url containing referer & embed hostname , the requested data is same as the normal metadata response)**

3. Georestrict rule apply to these videos , you can only use a Malaysia IP to get the HLS manifest.
4. Github Actions will download all channels's latest token everyday from my server in Malaysia and export to [here](https://raw.githubusercontent.com/samleong123/tonton_dailymotion_php/main/tv3_didiktvkpm_8tv_tv9_EPG.m3u8)
5. ~~**WARNING** : Dailymotion started to implement client's IP verification , TV3 is affected , so you might unable to watch TV3. <br> The only solution is watch it via [https://xtra.com.my/live-tv](https://xtra.com.my/live-tv) or use unifiTV~~ <br>
Use the latest playlist to resolve this issue. <br> The latest playlist will directly redirect you to Dailymotion HLS Manifest URL to generate the HLS bind with your IP Address (IPV4) <br> This redirection have a **rate limit** , you will get **429** if you hit the rate limit.

## Resolution 
### Last Updated : 15/4/2022

| Channels       | Resolution | Frame Rate | Bandwidth  | Platforms   |
|----------------|------------|------------|------------|-------------|
| TV3            | 1920*1080  | 25         | 2 - 5 Mbps | Dailymotion |
| DidikTV KPM    | 1920*1080  | 25         | 2 - 5 Mbps | Dailymotion |
| 8TV / 八度空间 | 1920*1080  | 25         | 2 - 5 Mbps | Dailymotion |
| TV9            | 1920*1080  | 25         | 2 - 5 Mbps | Dailymotion |
| Drama Sangat   | 1920*1080  | 25         | 2 - 5 Mbps | Dailymotion |

## How to use

### Build yourself :
1. Ensure PHP is installed on your web server , PHP 7.0 and above are recommended.
2. Copy the PHP file to ur web server and simply run it.
3. Create a valid M3U playlist and put this under the manifest URL
For example :
```
// FOR OTT Navigator & VLC ONLY : 

#EXTVLCOPT:http-user-agent=Mozilla/5.0 Windows NT 10.0; Win64; x64 AppleWebKit/537.36 KHTML, like Gecko Chrome/93.0.4577.82 Safari/537.36
#EXTVLCOPT:http-referer=https://www.dailymotion.com
#EXTINF:-1 group-title="Media Prima" ch-number="108" tvg-id="108" tvg-chno="108" tvg-logo="https://upload.wikimedia.org/wikipedia/en/thumb/f/fc/8TV_Chinese.png/220px-8TV_Chinese.png",8TV
https://xxxxx.com/8TV.php

// FOR USUAL IPTV PLAYERS (EXP : TIVIMATE / TVIRL) :
#EXTM3U
#EXTINF:-1 group-title="Media Prima" ch-number="108" tvg-id="108" tvg-chno="108" tvg-logo="https://upload.wikimedia.org/wikipedia/en/thumb/f/fc/8TV_Chinese.png/220px-8TV_Chinese.png",8TV
https://xxxxx.com/8TV.php|Referer=https://www.dailymotion.com|User-Agent=Mozilla/5.0 Windows NT 10.0; Win64; x64 AppleWebKit/537.36 KHTML, like Gecko Chrome/93.0.4577.82 Safari/537.36
```
4. An example of valid M3U playlist : [here](https://github.com/samleong123/tonton_dailymotion_php/blob/main/tv3_didiktvkpm_8tv_tv9_EPG.m3u8)

### Directly use prebuilt playlist: 
1. Insert the playlist URL [https://raw.githubusercontent.com/samleong123/tonton_dailymotion_php/main/tv3_didiktvkpm_8tv_tv9_EPG.m3u8](https://raw.githubusercontent.com/samleong123/tonton_dailymotion_php/main/tv3_didiktvkpm_8tv_tv9_EPG.m3u8) with any IPTV players you want (**except OTT Navigator**)
2. Use [https://github.com/samleong123/tonton_dailymotion_php/raw/main/tv3_didiktvkpm_8tv_tv9_EPG_ott.m3u8](https://github.com/samleong123/tonton_dailymotion_php/raw/main/tv3_didiktvkpm_8tv_tv9_EPG_ott.m3u8) for **OTT Navigator ONLY**.


## Common Issue :
1. 403 Error :
- Please ensure you are using **Malaysia's ISP network** and **not other country's ISP network**. <br> Media Prima **geo-restricted these livestream to Malaysia only**. <br> **Use VPN if you need to watch outside of Malaysia**.
- **Clear cache** of your IPTV apps and **reload / update** the playlist. <br> This playlist will be **updated each 1 hour** via Github Actions. <br> Always **make sure to get the latest version** of the playlist in order to **get the validated token from Dailymotion server**.
- Use **tested IPTV players** (e.g: **Tivimate** & **OTT Navigator** & **Kodi**)

2. Other Issue :
- **Create a issue** and **NOT message me through my social media** about your problem

## Credit :
Special thanks to [@jvloo](https://github.com/jvloo) for fixing the PHP script!
EPG source from : [weareblahs](https://github.com/weareblahs/epg)

## Screenshot :
![image](https://user-images.githubusercontent.com/58818070/163546968-dcb6c5b8-1823-4388-90ab-55ef9c9dec34.png)

![Cover](https://rtm.samsam123.tk/Channel%20Logo/rtm_logo.46f5fe40.png)
# RTM Live
Watch 8 RTM Channel : TV1 , TV2 , TV Okey , Berita RTM , Sukan RTM , TV6 , Parlimen Dewan Rakyat , Parlimen Dewan Negara on any IPTV players

## Before you use this playlist
1. This playlist uses manifest from RTM official online streaming website : https://rtmklik.rtm.gov.my 
2. This playlist **isn't geo-restricted** , you can play it with any country IP.
3. This playlist **isn't affiliated with https://rtmklik.rtm.gov.my  !**
4. This playlist uses ```#EXTVLCOPT:http-referrer & #EXTVLCOPT:http-user-agent & |Referer``` to define the correct referer and user-agent. Your IPTV player must support these tags in order to let this playlist work smoothly.
5. Date & Time in UTC+08 when the EPG is downloaded to this repo via Github Actions is available at [here](http://rtm.samsam123.tk/Date%20%26%20Time%20UTC%20%2B08.txt).

## Where to get this playlist
Add this url : [https://rtm.samsam123.tk/rtm-live.m3u8](https://rtm.samsam123.tk/rtm-live.m3u8) into your favourite IPTV apps and you are good to go.

## EPG
This playlist contain EPG from [weareblahs/epg/rtmklik.xml](https://github.com/weareblahs/epg/raw/master/rtmklik.xml).

This playlist use mirrored version located at [samleong123/rtm-live/rtmklik.xml](https://rtm.samsam123.tk/rtmklik.xml).

Github Actions of this repo will download the EPG from [weareblahs/epg/rtmklik.xml](https://github.com/weareblahs/epg/raw/master/rtmklik.xml) everyday.

Channel code/number in this playlist:
1. TV1 - RTMK01
2. TV2 - RTMK02
3. TV Okey - RTMK03
4. Berita RTM - RTMK04
5. Sukan RTM - RTMK05
6. TV6 - RTMK06
7. Dewan Rakyat - RTMK07
8. Dewan Negara - RTMK08

## Available Channels
This playlist contains channel below :
1. TV1
2. TV2
3. TV Okey
4. Berita RTM
5. Sukan RTM
6. TV6
7. Dewan Rakyat
8. Dewan Negara

## Manifest 
This playlist **contain 8 channels with HLS + MPEG-DASH manifest.** 

## Issue
Create an issue if you experienced any problem that didn't stated in README.md

## Credit
1. [weareblahs](https://github.com/weareblahs)
2. [rtmklik](https://rtmklik.rtm.gov.my)

![Cover](https://play-lh.googleusercontent.com/pvoIUgtbvS3XuxLTDkDOghF59twl66Vx-aalb74yOTKYLz3t17y7MJFtbwTfV0itWA)
# mewatch.sg

## Before you use this playlist
1. This playlist require supported IPTV Players to play it.

2. This [Widevine Key + Key ID](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_key.m3u8) playlist is **based on Widevine Key ID + Key exploit**, so license URL doesn't needed in this cases.

3. This [Widevine URL](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_url.m3u8) playlist is **based on API from meWatch**, license URL will be downloaded from meWatch API everyday, this playlist is still in experiement stage, please create an issue if you have any problem with this playlist.


4. Since Tivimate 4.0.0 supports Clearkey and thanks to [AqFad2811](https://github.com/AqFad2811) pointed out for the Clearkey URL format, i wrote a tool that can [convert Clearkey from Hex string to Base64 and output the JSON format that same as Clearkey License URL](https://github.com/samleong123/heroku-clearkey-hex-base64-json).

[Widevine Key + Key ID](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_key.m3u8) : **May not working once Google revoke the Widevine CDM version that contains exploit** or **Mediacorp re-encrypt it with different Widevine Key ID + Key.**

[Widevine URL](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_url.m3u8) : **May not working once meWatch started to block retrieving API without authentication** or **There's many users using this Widevine URL in the same time**

5. This playlist **isn't geo-restricted** , you can play it with any country IP.

6. This playlist **isn't affiliated with https://mewatch.sg !**

## Web Player
1. You can watch your favourite channel from meWATCH on [https://mewatchsg.samsam123.name.my/web-player](https://mewatchsg.samsam123.name.my/web-player)
2. This web player only supports Google Chrome / Microsoft Edge (Chromium) on Windows / Android / macOS. iOS and iPadOS isn't supported!

## EPG
[Widevine URL](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_url.m3u8) version containing Singapore EPG from [AqFad2811](https://github.com/AqFad2811).


## Available Channels
[Widevine Key + Key ID](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_key.m3u8) contains channel below :
1. Channel 5
2. Channel 8
3. Channel U
4. Channel Suria 
5. Channel Vasantham 
6. CNA
7. oktolidays
8. Global Citizen
9. EGG Network
10. meWATCH LIVE 1 
11. meWATCH LIVE 2

[Widevine URL](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_url.m3u8) contains channel below :
1. Channel 5
2. Channel 8
3. Channel U
4. Channel Suria 
5. Channel Vasantham 
6. CNA

## Beijing 2022 Olympics
Watch it via [Widevine URL](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_url.m3u8) or [Web Player for Beijing 2022](https://mewatchsg.samsam123.name.my/beijing2022). <br>
Web player only work for Windows / Android / macOS with Chrome / Edge or Widevine supported browser

## Tokyo 2020 Olympics
[olympics_tokyo_2020_mewatch_sg.m3u8](https://mewatchsg.samsam123.name.my/olympics_tokyo_2020_mewatch_sg.m3u8)

This playlist contains Opening Ceremony + Closing Ceremony series from MediaCorp SG.

## Issue
You may use any of the player below to play [Widevine Key + Key ID](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_key.m3u8) version.
1. Tivimate 4.0.0
2. OTT Navigator (Should work) 

or 

You may use any of the IPTV player that support Widevine URL to play [Widevine URL](https://mewatchsg.samsam123.name.my/mewatchsg_drm_wv_url.m3u8) version.

Example :

1. Tivimate
2. OTT Navigator
3. TVirl


**Create an issue if you found out another IPTV Players work!**

Create an issue if you experienced any problem that didn't stated in README.md

## Credit
1. [weareblahs](https://github.com/weareblahs)
2. [mewatch.sg](https://mewatch.sg)
3. [AqFad2811](https://github.com/AqFad2811)
4. [Clearkey Hex to Base64 Converter](https://github.com/samleong123/heroku-clearkey-hex-base64-json)

Now you can AqFad m3u Malaysia Singapore Indonesia MYSG 
www.astro.com.my www.astrogo.com.my www.playtvunifi.com.my

## bit.ly github.com links.astradamy.com t.me
https://bit.ly/iptv9mirror 
https://bit.ly/tipsproiptv
https://bit.ly/aqfadtvepg 
https://github.com/MYZARtv
https://github.com/azrinahmademuri
https://github.com/PortableTV
https://github.com/DarkSide2109
https://github.com/androidrepublica
https://github.com/Ajis199494
https://links.astradamy.com/NJOI
https://t.me/+XNI7qR2Gp305YTJl
https://t.me/+kGE4Jz-Cn3phMGVl
https://links.aqfadtv.xyz/Ont57nx8
https://bit.ly/Nuraincantik
https://links.astradamy.com/9Ul1KPOT
https://bit.ly/MuFakh-m3u
http://axcestv.vip:8080/get.php?username=freeview&password=axcestv&type=m3u_plus
https://bit.ly/Livetv-1234
https://t.me/+IsJSyg2SD9JhMGU1
https://github.com/search?q=astradamy&type=code
https://raw.githubusercontent.com/malaysianiptv/TEST-/main/1
https://t.me/+8q7bbfX6dP03NzVl
t.me apk TiviMate TVirl Kodi OTT Navigator
https://links.astradamy.com/hVQtGaR2
https://raw.githubusercontent.com/DarkSide2109/MuZu/main/index.html
http://www.natari-iptv.ueuo.com/Natari-iptv
github.com/Abdaziz1994
https://bit.ly/Livetvmovieje
https://calm-rain-70b4.buntai.workers.dev/0:/movie/Tombiruo720.mp4
https://raw.githubusercontent.com/Abdaziz1994/Abdaziz1994/main/HTB%20Lokal%20Wenak
https://youtu.be/VAQpk_bmqHg
https://byrl.me
https://bit.ly
https://yamcode.com
https://pastebin.com
https://github.com
Astro-unifi-TV-MYTV-RTMKlik-meWATCH-
Astro Channel 101-877 Unifi TV Channel 100-998 myFreeview Channel 101-725
epg
https://bit.ly/aqfadtvepg 
https://weareblahs.github.io/epg/astro.xml 
https://weareblahs.github.io/epg/unifitv.xml
https://weareblahs.github.io/epg/mytv.xml
https://weareblahs.github.io/epg/rtmklik.xml
https://raw.githubusercontent.com/AqFad2811/myiptv/main/singapore.xml
https://raw.githubusercontent.com/AqFad2811/myiptv/main/indonesia.xml
https://raw.githubusercontent.com/AqFad2811/myiptv/main/astro.xml
https://raw.githubusercontent.com/AqFad2811/myiptv/main/mytv.xml

github.com 
https://github.com/PortableTV
https://github.com/azrinahmademuri
https://github.com/MYZARtv
https://github.com/androidrepublica
https://github.com/DarkSide2109
https://github.com/Ajis199494
https://github.com/kechik92

m3u
https://yamcode.com/raw/untitled-59785
https://yamcode.com/raw/untitled-5751
http://muzu09.freevar.com
https://ayuh.jomlah.download/private-stuff/chika.mp4
https://yamcode.com/raw/malay-5361
https://bit.ly/MuFakh-m3u
https://bit.ly/B-m3u
https://bit.ly/2UepJdK
https://bit.ly/3vuni5o
https://yamcode.com/raw/fixlancar2
http://tiny.cc/cy9huz
http://iptv.tvmalaysia.cc:80/get.php?username=845197&password=845197&type=m3u_plus
https://yamcode.com/raw/muzuiptv-3
https://bit.ly/mewatchurl
RTMKlik Tonton Astro Unifi TV MyFreeview 

# iptv-malaysia

Asian shortlist IPTV channels from all over the world.

Internet Protocol television (IPTV) is the delivery of television content over Internet Protocol (IP) networks

## Usage

To watch IPTV you need to copy this link `https://haqem.github.io/iptv-malaysia/index.m3u` and paste at your M3U Player. *will update later.

You have a choices to shorlist your IPTV by country:
- `https://haqem.github.io/iptv-malaysia/malaysia.m3u` All Malaysian channels.
- `https://haqem.github.io/iptv-malaysia/indonesia.m3u`All Indonesian channels.
- `https://haqem.github.io/iptv-malaysia/singapore.m3u`All Singapore channels.
- `https://haqem.github.io/iptv-malaysia/japan.m3u` All Japan channels.
- `https://haqem.github.io/iptv-malaysia/korea.m3u` All Korea channels.
- `https://haqem.github.io/iptv-malaysia/asia.m3u` All Asia channels.

## Resources

All resources can be find at this repository [github.com/iptv-org](https://github.com/iptv-org).

## Legal

No video files are stored in this repository. The repository simply contains user-submitted links to publicly available video stream URLs, which to the best of our knowledge have been intentionally made publicly by the copyright holders. If any links in these playlists infringe on your rights as a copyright holder, they may be removed by sending a pull request or opening an issue. However, note that we have **no control** over the destination of the link, and just removing the link from the playlist will not remove its contents from the web. Note that linking does not directly infringe copyright because no copy is made on the site providing the link, and thus this is **not** a valid reason to send a DMCA notice to GitHub. To remove this content from the web, you should contact the web host that's actually hosting the content (**not** GitHub, nor the maintainers of this repository).
