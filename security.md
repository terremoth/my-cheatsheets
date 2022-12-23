# Information Security

## Logical Security

- Put a password to access your BIOS
- Enable TPM
- Enable secure boot so it will prevent malwares and ramsonwares before boot
- If available, put a password to access any disk after the BIOS
- Encrypt your disk to secure all your entire data even if you lost or someone steals, won't be able to know what's inside the disk
- Add a password to access your desktop area, if possible, use your fingerprint or eyes to unlock
- If possible pay to a VPN service (like NordVPN or Surfshark)
- Use Linux or BSD as your main operating system
- Always use a password manager, like Bitwarden (free and open source) to manage your passwords and keys
- When you have to create a new account, generate a big, random password containing all kind of characters and save it in your password manager
- Set your default DNS being the CloudFlare ones: 1.1.1.1 and 1.0.0.1 that uses DNS over HTTPS;
- Use 2FA always as possible, but avoid use SMS and Email as the 2nd factor, try to use a authenticator app you can download everywhere.  
  If your email was compromised or you don't have SMS cover area, you won't be able to access your account with 2FA
- Use Brave Browser, ToR Browser, Otter Browser or GNU Icecat as your default Web Browser because they are privacy/security intended
- Use StartPage and DuckDuckGo as search engine instead of Google, that tracks your data
- Config your operating system to delete temp data and cache data from time to time
- If you use Ubuntu Linux, enable Livepatch to fix kernel security issues automatically and without rebooting
- If you use windows let all your security options setted to High and Windows defender enabled.  
  If you're on Linux, download and use rkhunter and chkrootkit with crontab to periodically check for malware. You can also use ClamAV as antivirus.
- Make periodic encrypted backups/snapshots (timeshift on Linux for eg.) of your important data and send to a cloud backup service like Backblaze and also to a physical disk you own away from the internet 
- Use WOT (web of trust) and adblocker extensions in your web browser
- For linux users: use btrfs as default filesystem if you don't want to use LVM encrypted, so you can easily and quickly rollback backup snapshots.
- Always maintain your operating system updated so any security flaw can be fixed as soon as identified and patched
- If you're on Linux, never set a NOPASSWD in the sudoers file for root or you
- Install [Cerberus App](https://www.cerberusapp.com/) in your phone, so if someone steals, you can remotely delete all the data and let your cellphone unusable.
- If you don't want to use adblock or vpn blocker, consider using a [custom hosts file updated](https://github.com/StevenBlack/hosts) that cut off all the ads, malwares and trackers
- There is also another option to avoid ads, malwares and trackers that is the best option in my opinion: buy a raspberry pi zero, set up and use a PI-Hole on it,  
  so it wiil be like a minimal O.S. filtering any ads, malware or trackers before came to your device

## Physical Security
- Always let your headset microphone switch OFF if it has the switch
- Buy a webcam protector and let your webcam always closed
- If you have a notebook/laptop consider to buy a security lock chain cable so 
- If/when possible, buy a NAS and put them to sync and regenerate your disks using only parts of the disks with the others,  
  so when the HDDs got corrupted it will warn you and you can replace the corrupted HDD for another, and this new one will be "regenerated/filled" by the others.
  (ALWAYS your disks will corrupt, It's not a matter of if will, it's WHEN)  

## Behavioural Security

- Never buy in websites that don't have HTTPS in their URL's
- Never click links in your emails unless you can see the true URL and know the sender. If in doubt, copy the text URL and put yourself in the web browser
- Prefer buy things using the store apps instead of the web
- Prefer to use apps that don't have ads, so they can't track you (what/when/how you're using your stuff)
- Always have in mind that are bad people always trying to hack you all the time, so never give them any chance to do this
- Never connect to password-unprotected WiFi because your data can be tracked and be seen. It is common to see WiFi public and open in hotels, airports and coffee shops
- Do not open files people send you in emails unless you are 100% sure that doesn't contain any malware. If in doube, ask your antivires or online antivirus services to scan before open

---

_If your data is not in your disks, it doesn't belong to you. As simple as that._  

If you use Google Account and put everything of your life on it, take care, Google sometimes arbitrarily removes the entire account of people, giving no explaination why.  
You can lose your youtube channel, drive data, docs and spreadsheets, keep (lists), photos, calendar, email account, password manager in one shot, forever!!!
