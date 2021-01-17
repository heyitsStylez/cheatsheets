# Bash Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

```bash
find / -name testfile.txt 2> /dev/null                          # Find a file from root and its sub directories, ignore permission errors	
find / -type f -size +30M | xargs -p tar -czvf                  # Find files that are above 30MB and compress	
du -h -d 1 / 2>/dev/null                                        # Dsplay the size for all of the top-level directories in root directory	
du -ahx . | sort -rh | head -5                                  # Find top 5 largest files and directories, sorted
echo "" > api-search_ID_debug.log                               # Write empty string into file. Usually used to empty a large log file
scp -r username@from_host:/remote/directory/ /local/directory/  # Copy directory from a remote host to local host	
scp file.txt remote_username@10.10.0.2:/remote/directory        # Copy file from local to remote
sudo killall -HUP mDNSResponder                                 # Flush DNS
cat /etc/*_version /etc/*-release && uname -a                   # Get information about Linux distribution
php --ini                                                       # Get php configuration files
php -i | grep <variable>                                        # Get specifi php environment variables
timedatectl set-timezone Asia/Kuala_Lumpur                      # Set timezone to +8GMT
hwclock -s                                                      # Set local/system time to follow RTC time.
```