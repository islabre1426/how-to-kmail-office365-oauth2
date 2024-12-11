# Workaround for KMail to use Office 365
(Tested on KMail 24.08.3)

For unknown reason, KMail cannot configure Office 365 automatically.
IMAP option does not work, [Exchange one has a bug which is not yet resolved](https://bugs.kde.org/show_bug.cgi?id=409183).

Nevertheless, Exchange is the only thing that works.

At the mean time, try the following workaround:
- Settings > Configure KMail.. > Accounts > Identities > Add..: Fill needed information (Name and Email Address) > OK.
- In the same window, go to Receiving > Add... > Custom Account... > Choose Microsoft Exchange Server (EWS).
- Fill Account Name and Email, for domain use outlook.office365.com. Also fill Username and Password (it will fail since OAuth2 is forced).
- Uncheck Server Autodiscovery and manually input EWS URL (if your provider doesn't change it, the default is https://outlook.office365.com/EWS/Exchange.asmx).
- Click OK (it will say it is not working and whether you want to save it, click OK and Save respectively).
- Reopen the created account to modify it.
- Check OAuth2 (Office 365) > Click OK. The OAuth2 prompt will show up.
- Finish it and the incoming account is set.
- Go to Sending and click Add...
- Choose EWS, the account you just verified will show up, choose it and outgoing account is set.
- Everything should now work.

Credit to:
- [KDE's Userbase](https://userbase.kde.org/Kmail/Configuring_Kmail/Accounts/Office_365) for documenting.
- [gzqx](https://github.com/gzqx/how-to-kmail-office365-oauth2) for original workaround.
