# sshd-google-authenticator
Config files for using FreeBSD with Google Authenticator to challenge and reply on ssh logins

# Use of these files
These files are used with the installation of the pam_google_authenticator port on FreeBSD.  The desired result is to configure the prompting on login for an ssh key followed by a verification code.  

These files are the result of working some tutorials on configuring Google Authenticator for use with FreeBSD sshd.  They are not meant to be complete instructions for the installation of those programs.  These sample config files are provided because most example configurations used passwords instead of ssh keys.

# Warnings
Incorrect configuration of these files can result in a few kinds of failures.  They include:
- continuous prompting for a password, even if one was not set
- no acceptance of values provided
- acceptance of values provided, but ending in a prompt for a password even if one was not set.

# Safeguards
When configuring Google Authenticator for use with SSH logins, it is helpful to maintain more than one connection to the host.  It can be easy to lock yourself out of the computer with a bad config.  We recommend a recent backup and more than one pattern in to the host, if possible.

# google_authenticator_etc_ssh_sshd_config.txt
This file holds example values for use with pam_google_authenticor port on FreeBSD.
Editing a file stored in /etc/ssh/sshd_config will allow Google Authenticator programs to prompt for a verification code.  This configuration is for use with an ssh key.  This config file will wire in Google Authenticator and ssh keys to the daemon.

# google_authenticator_pamd_sshd.txt
This file further coordinates actions of Google Authenticator with sshd.  This particular combination of settings will allow the ssh daemon to prompt for an ssh key and then a verifcation code from Google Authenticator.  It will not prompt for a password.  
