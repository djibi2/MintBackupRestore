01st of June, 2014
Overview:

1.) Introduction: For what are these scripts good for?
2.) How to use the scripts
3.) Sources that have contributed to the development
4.) Frequently asked questions (FAQs) & Possible upcoming questions (PUQs)
5.) Contact information of the author
6.) md5 checksums of the files
7.) CAUTION: Upgrading from Linux Mint 16 to Mint 17 (Bug)


1.) Introduction: For what are these scripts good for?
------------------------------------------------------------------------------------
Linux Mint is a great operating system, but since updates are frequent, maintaining 
the system can cause a lot of work. In contrast to Ubuntu, Linux Mint is more in favor 
of reinstalling the entire system with every new release, rather then upgrading.
But I slightly prefer Linux Mint, because I can use flash, Java and playback DVD right 
out of the box. Installing a new release is quite quick, but getting the settings 
(such as fstab, cronjobs, etc.) back to how I like them takes me usually 1-2 days.

So I decided to write two scripts: 
a.) Backup_Linux_Settings:
Saves all the current settings, installed packages, data stored in home folder and 
tweaks you have done to the system.

b.) Restore_Linux_Settings
Script which restores these "settings" into your new freshly installed Linux Mint.
 


2.) How to use the scripts
 ------------------------------------------------------------------------------------
 >>Backup_Linux_Settings<<
 a.) download both scripts and store them wherever you like
 b.) take your standard editor (in Linux Mint it's >>Pluma<<) and open the file (or just 
	 click on it and select "Display")
 c.) modify the "destination" were you want to store your backups in the file(line 31 in 
	 backup script). In my case this is "/media/Daten/Linux_Backup/". Please don't make
	 the mistake to backup into the same partition you will install the new Linux version
	 later on.
 d.) start the script in your terminal with > sudo bash Backup_Linux_Settings_v4.sh
     Please make sure you are in the same folder as the script is.
	 
a.), b.), c.) you only have to do once in your life. d.) you do every time you want to backup

 >>Restore_Linux_Settings<<
 a.) take your standard editor (in Linux Mint it's >>Pluma<<) and open the file (or just click on
	 it and select "Display"). 
 b.) modify the folder were you have stored your backups (source). You can find this setting in 
	 line 32 of the restore script. Note you only should define the path (e.g. "/media/Daten/Linux_Backup/")
	 and NOT the file (e.g., do NOT do: "/media/Daten/Linux_Backup/mybackup.zip")
 c.) start the script in your terminal with > sudo bash Restore_Linux_Settings_v9beta.sh
     Please make sure you are in the same folder as the script is. Also take a look at the screenshot
	 provided.
 d.) follow the directions on the screen.
 
NOTE: At one point you will be asked "to restore all settings" or "to restore only selected settings". 
If you have changed the Distribution (e.g, from Linux Mint Maya 13 to Mint Petra 16) it is strongly 
advised NOT to chose "restore all settings". This might lead to incompatibility of some settings between 
the versions. But don't worry "restore only selected settings" will restore already a whole lot. However, 
"to restore all settings" can be chosen if you are in the same Linux Mint Version and just want to restore
former settings. You also have the option only to "restore your former packages only" or to "only restore 
Firefox and Thunderbird settings". Take a look at the provided screenshot.
 
 a.), b.) you only have to do once in your life. c.) you do every time you want to restore
 
 
 
3.) Sources that have contributed to the development
------------------------------------------------------------------------------------
If you want to understand the scripts please visit the following websites:
http://askubuntu.com/questions/9135/best-way-to-backup-all-settings-list-of-installed-packages-tweaks-etc
http://www.techradar.com/news/software/operating-systems/the-pain-free-guide-to-switching-linux-distros-478667
http://askubuntu.com/questions/9135/best-way-to-backup-all-settings-list-of-installed-packages-tweaks-etc
http://debiananwenderhandbuch.de/dpkg.html
http://community.linuxmint.com/tutorial/view/2
http://www.gnu.org/software/coreutils/manual/html_node/cp-invocation.html
http://unixhelp.ed.ac.uk/CGI/man-cgi?cp
http://linux.die.net/man/1/zip
http://linux.die.net/man/1/unzip
http://askubuntu.com/questions/1705/how-can-i-create-a-select-menu-in-a-shell-script
http://www.linuxjournal.com/content/bash-arrays
http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html
http://www.linuxidentity.com/us/down/articles/Backup_TBoL9_EN_www.pdf
http://www.thegeekstuff.com/2010/06/bash-array-tutorial/
http://www.evbackup.com/support-commonly-used-rsync-arguments/
http://rsync.samba.org/ftp/rsync/rsync.html
http://www.dotnetperls.com/7-zip-examples
http://flyingtomoon.com/2012/04/04/unzip-a-specific-folder-of-a-compressed-file-exclude-some-folders-from-extraction/
http://readwrite.com/2013/10/02/github-for-beginners-part-2#awesm=~oEBUQPMUDkYjD6




4.) Frequently asked questions (FAQs) & Possible upcoming questions (PUQs)
------------------------------------------------------------------------------------
a.) There are thousands of backup programs out there. Even Linux Mint has the "Backup Tools" 
	why would anyone use this script?

Well here are my thoughts on backing up my Data and Operating Systems: First of all I 
strictly differentiate between a.) backing up my personal data and b.) backing up my 
operating system (with its settings and updates). For Microsoft Windows (all versions) 
I prefer Clonezilla (http://clonezilla.org/). Once I have set up my Windows system with all
settings, drivers and updates a make a image using Clonezilla (before I install any programs). 
When my system starts getting slower because I have updated to a new Anti-virus Program, I can 
quickly get back my "fresh and fast" new Windows installation within 10 minutes when 
reinstalling the image with Clonezilla. Because new Linux Distros like Linux Mint come out
so quickly (every 6 months, were as MS Windows XP was out there for 12 years), I don't usually
reinstall an image with Clonezilla containing the old version of Linux but install the new current
Linux Mint distribution. But then all my settings to the Desktop and Programs are gone (e.g., fstab) 
and I have to adjust everything again by hand. I speed this up with this script. Because I
like how it works, I thought I share it. Why don't I use the "Backup Tools" of Linux Mint? 
Well I don't like the fact that I have to choose which files I have to back up each and every time. 
And rather then programming a new Backup Tool, why not use the software that comes with Mint in
the first place, using a simple script?

Now coming back to backing up my data rather then the operating system. I do not recommend to 
use this program to backup your data. The scripts will backup your data in the home folder and restore
them, but there are better programs to make backups of your data. If you have a server rather than a
desktop I have good experience using rsnapshot (http://www.rsnapshot.org/). You will have incremental
backups only using little new disc space (because rsnapshot uses hard links).I don't like this program
on desktops, because (even when using Anachron to schedule the backups) rsnapshot gets confused 
if you shut down the system while it is running. For desktops I prefer rsync (http://rsync.samba.org/)
run with a script to ensure proper settings and asking me (Zenity, https://help.gnome.org/users/zenity/stable/)
before it starts the backup and telling me when it is finished. Note that I store my data on a
special data partition rather then in the home folder of Linux. But it will also work for your home folder 
if you have your data there. If you want to have that script too, just write me.


b.) Why do you backup so much stuff using  >>Backup_Linux_Settings<< and not just what you need?

Well the backup will be around 220 Mb big, if you have no personal data in your home folder. 
Considering that todays hard drives have 2Tb and above I thought backup as many settings as Linux has. 
That way we don't miss anything. It's true that the  >>Restore_Linux_Settings<< script only cherry picks 
the most important settings. But the script will ask you if you want to restore everything and if you are
an "advanced user", you can add what you want to restore in the >>Restore_Linux_Settings<< script.
Also take a look at this forum: http://www.techradar.com/news/software/operating-systems/the-pain-free-guide-to-switching-linux-distros-478667


c.) Why do you use the zip command in your script to backup the files and not 7zip?

Actually I would prefer to use 7zip. It compresses higher, used multiple threads (faster) and 
has higher encryption (AES256 rather than ZipCrypto). The current script uses the:
"zip -r -y -u -e $destination$version /etc/" command. In principle this could be replaced 
with: "7za u -p -mmt=3 $destination$version.7z -r /etc/". Please refer to "http://linux.die.net/man/1/zip"
and "http://www.dotnetperls.com/7-zip-examples" to understand what that means.
But when I run 7zip like that on the home folder the 7zip program starts to backup other folders that
are not in home???? According to the manual it should NOT follow hard and soft links by default and just store
them as links. It could be a bug of 7zip. Zip on the other hand has the "-y" option, which solves this issue. 
An additional advantage could be that zip is compatible with nearly all operating systems. You can easily check
 if your backup went well by looking into the zip file generated by the script.

 
d.) Why do you use the zip command in your script to backup the files and not rsync?

There is a very simple answer to that. If my partition where I store my Data would be EXT3 or 
EXT4 (file system), I would have probably written the script using rsync rather then zip.
rsync has the great advantage that in can maintain the owners and permissions of the files 
(Whereas zip can only save the permissions (owner will be the guy who makes the zip file)).
But this is only true if you use EXT file systems. My Data drive has NTFS, because I also want to read
the partition when I am using Windows (in some cases I just still need Windows). Ubuntu and thus also
Linux Mint mount NTFS partitions and all of its contents (files and folders) as "root root rwxrwxrwx".
So again you loose your owners and permissions and additionally everyone on the system can modify your 
backup files (security!), when I use rsync. When using zip we can at least set a password. The backup script
will ask you to choose one. An additional benefit is that using zip, your backup will be smaller then using rsync.
Even though this is not so important with current hard drive sizes (>2Tb).


e.) Does your script maintain the correct owners and permissions of the files and folders is backs up?

Here is how I tried to solve this important topic. Maybe someone has a better idea? Because we make a zip
file of your settings, we lose the owners (but not the permissions) of your files. But we restore them by using
the "cp -rv --no-preserve=ownership --preserve=timestamps,mode $temp_dir/etc/cron.hourly/ /etc/" command. Hence
we will copy the content of your old files into the new files of your freshly installed Linux distribution. 
But using "--no-preserve=ownership" the owners will not be changed. Thus we use the owners the new freshly installed
Linux wants to see.


f.) Why does the script ask me for a password?

Please see answer d.) above. I is just for security. If you don't want to set a password, just press enter
without entering anything. And yes, you have to remember your password if you want to restore.


g.) Is this script really stable?

The "backup script" is very stable. I have used it many many times on different Linux versions. It is also not
possible to make any damages with this script. Thus I released it as stable. Since it produces a zip file you can 
open it later on by hand and restore by hand. 
The "restore script" I released as beta, because it makes changes to your system. I have used it also many times
without any problems, but I cant 100% assure that this is true on each and every computer in this world. Also I
have not received any complaints so far (01.06.2014) from users worldwide (around 100 downloads).
If you want to be very safe you can use the backup script first on the new installed distro.
Then if the restore script makes some changes you don't like you can restore the backup of the new system. 
Also the current version of the restore script has several restore options (you will be asked this during restore process). 
I would not use the "restore all settings" option when moving to a new version. The second option only restores selected settings. 
This is already much safer. But you can also just restore Firefox and Thunderbird to test that the script works correctly.
This is also very safe (for your system) but of course you don't get back every setting.
Thus it would be great if a lot of people are willing to test the beta script. The more
positive or negative feedback I get, the more I can improve the scripts. 
If you want to be even more safe you can use Clonezilla (http://clonezilla.org/) to make an image of your fresh installed Linux 
version. Then if this script unexpectedly does something completely wrong (very unlikely) when playing in the old settings of
the former Linux version, you can reinstall the image in 10 min and everything is back 100% to the fresh install.

BTW, I do not recommend the script to make backups of your data! The scripts are intended to backup and restore the 
settings (even if the entire home folder will be backed up with the script.)


h.) What does the script back up?

It backs up the entire "home" folder, the entire "etc" folder (in encrypted form), a list of all of your installed packages,
a list of the most important installed packages (e.g., without development packages), your repro keys and your sources lists 
(take a look at the script it is easy to read).


i.) You as the scriptwriter, how much did you used the script and how many times performed a successful backup and restore?

I didn't count but maybe 20-40 times (Mint 16)? What I am missing are even more beta testers on other systems...go for it.
It works stable and fine on my system.
Additionally, I have used the same commands that are used in the scripts to recover settings from Linux Mint 13 to Linux Mint 16. 
This scripts are intended to speed it up and you don't longer have to remember all the commands and Google for hours
how to find the right way to do it.


j.) Would you use this for the upcoming Linux Mint 17?

I just used the restore script (version v8) to update from Mint 16 to 17 (1st of June, 6:55 pm o'clock). 
There are a few incompatibilities between the versions. I will fix this issue in the upcoming week. 
More details at the End of this document. Sorry for any inconveniences!


k.) What flavor of Linux Mint do you prefer (Cinnamon, Mate or others)?

I personally like Mate.


l.) Based on the content of your README in GitHub, you said that the zip extracts without the owner of the files. 
Does this ever caused a conflict in your tests?

No not yet. The copy function the script uses, copies the files with the correct rights, the owners it takes from the files 
that are already there. This could be a weakness of the scripts. But only if the setting
file you restore is not there in the new system. On the other hand, if it is not there in the new system then the new system will most 
likely not need it anyway. If someone has a neat idea to save the rights AND owners when backing up with zip then please post 
it as "new idea". A possibility could be to move away from the zip-format to 7zip or tar. But so far there are no 
complaints worldwide that the script does not work as intended (status 01.06.2014). An I have also not encountered
any difficulties. Still I release the restore script at beta, just to be correct. The project is still relatively 
and I want to get even more feedback before I release it as stable.




5.) Contact information of the author
------------------------------------------------------------------------------------
>>> bastian.noller'[please.dont.spam]'web.de <<<
Please replace '[please.dont.spam]' with an @ sign.




6.) md5 checksums of the files
------------------------------------------------------------------------------------
af73bfe13e2259cd9ee49e893eb76469  Backup_Linux_Settings_v3.sh (obsolete)
e88780ab134dbf6b5eb11fad3488a52d  Restore_Linux_Settings_v5beta.sh (obsolete)
20ae409a6456f88593a77b8c42c643f4  Backup_Linux_Settings_v4.sh
d8223f21adc5752406fb5bb3039f68fa  Restore_Linux_Settings_v6beta.sh (obsolete)
248baeb87f43c309ec767b09e89a1fc2  Restore_Linux_Settings_v7beta.sh (obsolete)
65be2c1c5a35e67bb95466c2441092c6  Restore_Linux_Settings_v8beta.sh (obsolete)
09484f1f5739388ef26ba877ed86408b  Restore_Linux_Settings_v9beta.sh





7.) CAUTION: Upgrading from Linux Mint 16 to Mint 17 (Bugs)
------------------------------------------------------------------------------------ 
The backup and restore scripts work perfectly when used within one 
version (e.g., Mint 16). Here a list of hiccups that will be fixed in the upcoming
weeks when transferring from Mint 16 to 17 (sorry for any inconveniences):

- Backup script works flawlessly as with other versions
- Restore script works fine when restoring Firefox settings
- Restore script on the other hand causes issues with files that are not already 
present on the system (e.g., old desktop icons). Reason: The owner of the 
files will be "root" because they weren't there before and the zip-format doesn't
preserve the original owner.

What does this mean? The restore function works fine for example for your
cronjobs, which are root owned anyway. It also works fine for example with
your fstab file because it is already there. I causes issues with for example 
Thunderbird. Because Thunderbird saves, due to security reasons, all files in
a random folder name. When you restore your old Thunderbird data this folder will
be owned by "root" because this random name was not already there.

How do you correct this (quick bug fix):

- go to your "/home/user" folder
- switch to terminal
- enter > sudo chown -R user:user .thunderbird/ 
- please replace "user" with your correct user name in the commands above

You can proceed similar with other files that have the wrong owners.
But it is annoying and I will fix this bug ASAP.

- When restoring your former fstab there can be an issue: If you install the new
Mint version into the same partition as your former Linux distribution,
Linux Mint 17 will format that partition. By doing this it changes the UUID of
that partition. When you restore your fstab from your former version be sure to
update the UUID of the formated partition in the fstab file. All other settings 
in the fstab will stay correct. 






