# Befor evaluation

1. Copy Debian.vdi via VirtualBox to the local machine

Leave the name Debian.vdi as it is.

2. Create signature.txt
```bash
sha1sum Debian.vdi
```
Save the number to signature.txt


3. Upload signature.txt to Git Repo

# Evaluation

1. Copy signature.txt from git to dir with Debian.vdi

2. Compare downloaded signature.txt with Debian.vdi's signature

```bash
diff <(sha1sum Debian.vdi | awk '{print $1}') <(awk '{print $1}' signature.txt)

```
3. Clone or Duplicate the VM To ensure a safe evaluation environment

Go to VirtualBox - Tools - Virtual Nedia Manager

Name: Debian2

4. Add Debian2 to VirtualBox
Add New - Select Use an existing virtual hard disk file

5. Add Rule 4242 shh in VirtualBox Network

6. Start Debian2

7. Go to another terminal and connet from there

# UFW

Check UFW status
```bash
sudo ufw status
```
Enable UFW
```bash
sudo ufw enable
```
Disable UFW
```bash
sudo ufw disable
```
Allow Traffic
```bash
sudo ufw allow 4242
```
Deny Traffic
```bash
sudo ufw deny 4242
```

# SSH

Check SSH status
```bash
sudo systemctl status ssh
```
Start SSH
```bash
sudo systemctl start ssh
```
Start Automatically on boot
```bash
sudo systemctl enable ssh
```
Stop SSH
```bash
sudo systemctl stop ssh
```
Disable SSH from Starting at Boot
```bash
sudo systemctl disable ssh
```
# User
Check that your user is within the "sudo"
```bash
groups username
```
Check that your user is within the "sudo"
```bash
getent group sudo
```
Check that your user is within the "user42"
```bash
getent group user42
```
Add new user
```bash
sudo adduser <username>
```
Add new group
```bash
sudo groupadd <groupname>
```
List all users
```bash
cat /etc/passwd
```
List all groups
```bash
getent group
```
Add user to a group
```bash
sudo usermod -aG groupname username
```
