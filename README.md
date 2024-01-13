# OneDrive mount on Windows 10 using rclone

## 1. rclone download

> [https://rclone.org/downloads/](https://rclone.org/downloads/)
>
> save to C:\rclone\rclone.exe

## 2. rclone config

> filename: %APPDATA%\rclone\rclone.conf

```
C:\rclone> rclone.exe config
e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q> n

Enter name for new remote.
name> OneDrive

Option Storage.
Type of storage to configure.
Choose a number from below, or type in your own value.
 1 / 1Fichier
   \ (fichier)
 2 / Akamai NetStorage
   \ (netstorage)
 3 / Alias for an existing remote
   \ (alias)
 4 / Amazon Drive
   \ (amazon cloud drive)
 5 / Amazon S3 Compliant Storage Providers including AWS, Alibaba, ArvanCloud, Ceph, ChinaMobile, Cloudflare, DigitalOcean, Dreamhost, GCS, HuaweiOBS, IBMCOS, IDrive, IONOS, LyveCloud, Leviia, Liara, Linode, Minio, Netease, Petabox, RackCorp, Rclone, Scaleway, SeaweedFS, StackPath, Storj, Synology, TencentCOS, Wasabi, Qiniu and others
   \ (s3)
 6 / Backblaze B2
   \ (b2)
 7 / Better checksums for other remotes
   \ (hasher)
 8 / Box
   \ (box)
 9 / Cache a remote
   \ (cache)
10 / Citrix Sharefile
   \ (sharefile)
11 / Combine several remotes into one
   \ (combine)
12 / Compress a remote
   \ (compress)
13 / Dropbox
   \ (dropbox)
14 / Encrypt/Decrypt a remote
   \ (crypt)
15 / Enterprise File Fabric
   \ (filefabric)
16 / FTP
   \ (ftp)
17 / Google Cloud Storage (this is not Google Drive)
   \ (google cloud storage)
18 / Google Drive
   \ (drive)
19 / Google Photos
   \ (google photos)
20 / HTTP
   \ (http)
21 / Hadoop distributed file system
   \ (hdfs)
22 / HiDrive
   \ (hidrive)
23 / ImageKit.io
   \ (imagekit)
24 / In memory object storage system.
   \ (memory)
25 / Internet Archive
   \ (internetarchive)
26 / Jottacloud
   \ (jottacloud)
27 / Koofr, Digi Storage and other Koofr-compatible storage providers
   \ (koofr)
28 / Linkbox
   \ (linkbox)
29 / Local Disk
   \ (local)
30 / Mail.ru Cloud
   \ (mailru)
31 / Mega
   \ (mega)
32 / Microsoft Azure Blob Storage
   \ (azureblob)
33 / Microsoft Azure Files
   \ (azurefiles)
34 / Microsoft OneDrive
   \ (onedrive)
35 / OpenDrive
   \ (opendrive)
36 / OpenStack Swift (Rackspace Cloud Files, Blomp Cloud Storage, Memset Memstore, OVH)
   \ (swift)
37 / Oracle Cloud Infrastructure Object Storage
   \ (oracleobjectstorage)
38 / Pcloud
   \ (pcloud)
39 / PikPak
   \ (pikpak)
40 / Proton Drive
   \ (protondrive)
41 / Put.io
   \ (putio)
42 / QingCloud Object Storage
   \ (qingstor)
43 / Quatrix by Maytech
   \ (quatrix)
44 / SMB / CIFS
   \ (smb)
45 / SSH/SFTP
   \ (sftp)
46 / Sia Decentralized Cloud
   \ (sia)
47 / Storj Decentralized Cloud Storage
   \ (storj)
48 / Sugarsync
   \ (sugarsync)
49 / Transparently chunk/split large files
   \ (chunker)
50 / Union merges the contents of several upstream fs
   \ (union)
51 / Uptobox
   \ (uptobox)
52 / WebDAV
   \ (webdav)
53 / Yandex Disk
   \ (yandex)
54 / Zoho
   \ (zoho)
55 / premiumize.me
   \ (premiumizeme)
56 / seafile
   \ (seafile)
Storage> 34

Option client_id.
OAuth Client Id.
Leave blank normally.
Enter a value. Press Enter to leave empty.
client_id>

Option client_secret.
OAuth Client Secret.
Leave blank normally.
Enter a value. Press Enter to leave empty.
client_secret>

Option region.
Choose national cloud region for OneDrive.
Choose a number from below, or type in your own string value.
Press Enter for the default (global).
 1 / Microsoft Cloud Global
   \ (global)
 2 / Microsoft Cloud for US Government
   \ (us)
 3 / Microsoft Cloud Germany
   \ (de)
 4 / Azure and Office 365 operated by Vnet Group in China
   \ (cn)
region> 1

Edit advanced config?
y) Yes
n) No (default)
y/n>

Use web browser to automatically authenticate rclone with remote?
 * Say Y if the machine running rclone has a web browser you can use
 * Say N if running rclone on a (remote) machine without web browser access
If not sure try Y. If Y failed, try N.

y) Yes (default)
n) No
y/n>

2024/01/13 10:06:01 NOTICE: If your browser doesn't open automatically go to the following link: http://127.0.0.1:53682/auth?state=yMSyCtR4xw5cBIDN5VSsNg
2024/01/13 10:06:01 NOTICE: Log in and authorize rclone for access
2024/01/13 10:06:01 NOTICE: Waiting for code...
```

< IMG >

```
2024/01/13 10:11:25 NOTICE: Got code
Option config_type.
Type of connection
Choose a number from below, or type in an existing string value.
Press Enter for the default (onedrive).
 1 / OneDrive Personal or Business
   \ (onedrive)
 2 / Root Sharepoint site
   \ (sharepoint)
   / Sharepoint site name or URL
 3 | E.g. mysite or https://contoso.sharepoint.com/sites/mysite
   \ (url)
 4 / Search for a Sharepoint site
   \ (search)
 5 / Type in driveID (advanced)
   \ (driveid)
 6 / Type in SiteID (advanced)
   \ (siteid)
   / Sharepoint server-relative path (advanced)
 7 | E.g. /teams/hr
   \ (path)
config_type> 1

Option config_driveid.
Select drive you want to use
Choose a number from below, or type in your own string value.
Press Enter for the default (9c49c0d10).
 1 /  (personal)
   \ (9c49c0d10)
config_driveid> 1

Drive OK?

Found drive "root" of type "personal"
URL: https://onedrive.live.com/?cid=9c49c0d10

y) Yes (default)
n) No
y/n>

Configuration complete.
Options:
- type: onedrive
- token: {"access_token":"EwCQA8l6BAAUs5+HQn0N+h2FxWzLS31ZgQVuHsYAAYhE63x7U7NHnmp8pvu4P","token_type":"Bearer","refresh_token":"M.C104_BAY.-CjXBnM2Z5!Jj13oliTbts!vX6Zylix5u3mIsjSAybDiW2mW4nYUNxrri2cyCstqduLNkFw0*H9GouZ","expiry":"2024-01-13T11:11:26.0089063+09:00"}
- drive_id: 9c49c0d10
- drive_type: personal
Keep this "OneDrive" remote?
y) Yes this is OK (default)
e) Edit this remote
d) Delete this remote
y/e/d>

Current remotes:

Name                 Type
====                 ====
OneDrive             onedrive

e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q> q
```

> copy rclone.conf to C:\rclone\

```
C:\rclone> copy %APPDATA%\rclone\rclone.conf C:\rclone\
```

## 3. WinFsp download

> [https://winfsp.dev/rel](https://winfsp.dev/rel/)
>
> Download WinFsp Installer, and install


## 4. rclone mount test

> filename: C:\rclone\rclone_mount.bat
 
```
@echo off
rem filename: rclone_mount.bat

C:\rclone\rclone.exe mount OneDrive: G: --config "C:\rclone\rclone.conf" --log-level=INFO --log-file="C:\rclone\rclone_mount.log" --cache-dir C:\rclone --dir-cache-time=48h --vfs-cache-mode full --vfs-read-chunk-size=32M --vfs-read-chunk-size-limit=2G
```


## 5. Download NSSM

> download nssm
> [https://nssm.cc/download](https://nssm.cc/download)
>
> save to C:\rclone\nssm.exe

> Usage:
```
C:\rclone> nssm.exe
NSSM: The non-sucking service manager
Version 2.24 64-bit, 2014-08-31
Usage: nssm <option> [<args> ...]

To show service installation GUI:

        nssm install [<servicename>]

To install a service without confirmation:

        nssm install <servicename> <app> [<args> ...]

To show service editing GUI:

        nssm edit <servicename>

To retrieve or edit service parameters directly:

        nssm get <servicename> <parameter> [<subparameter>]

        nssm set <servicename> <parameter> [<subparameter>] <value>

        nssm reset <servicename> <parameter> [<subparameter>]

To show service removal GUI:

        nssm remove [<servicename>]

To remove a service without confirmation:

        nssm remove <servicename> confirm

To manage a service:

        nssm start <servicename>

        nssm stop <servicename>

        nssm restart <servicename>

        nssm status <servicename>

        nssm rotate <servicename>
```

## 6. Install Windows Service

```
C:rclone> nssm.exe install rclone_mount
Administrator access is needed to install a service.
```

< IMG >

Environment variables such as %APPDATA% do not apply. Enter the Full Path.

> Path: C:\rclone\rclone.exe
> 
> Startup directory: C:\rclone
> 
> Arguments: mount OneDrive: G: --config "C:\rclone\rclone.conf" --log-level=INFO --log-file="C:\rclone\rclone_mount.log" --cache-dir C:\rclone --dir-cache-time=48h --vfs-cache-mode full --vfs-read-chunk-size=32M --vfs-read-chunk-size-limit=2G
