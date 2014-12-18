Jailbreak (Windows)
===================

For a newer and open-source version of these tools please see 
https://github.com/iSECPartners/jailbreak

Written by: andreas _[at]_ isecpartners.com and cclark _[at]_ isecpartners.com

Jailbreak exports certificates marked as non-exportable from the Windows 
certificate store.  This can help when you need to extract certificates 
for backup or testing. You must have permissions to use the private key on the 
filesystem in order for jailbreak to work -- Jailbreak cannot keys stored
on smartcards.

Tested On: 
----------

* WinXP SP2 x86
* Win2k3 SP1 x86
* Vista RTM & SP1 x86
* Vista RTM x64 (jbstore only!)
* Windows 7 x86
* Windows 7 x64 (jbstore only!)

Note: Win2k does not work. 

Instructions
------------

1. Extract the files from the Jailbreak zip.
2. Run jailbreak.exe while running as administrator
3. A mmc with the Local Machine and Current-User Certificate snap-ins will load
4. All certificates are now marked as exportable
5. Use the certificate UI to export certificates and their private keys. 

Note: If you get an unhandled exception, email andreas.  It is probably a bug
in Jailbreak.

Other Included Tools
--------------------

### jbcsp

jbcsp exports keys that are contained within the CSP and not associated with a
certificate. jbscp requires .NET Framework 2.0.

Run: 
`jbscp "Key container" "output file name" [-u]`

-u is an optional parameter and will export from the user store instead of the
machine store.

### jbstore

JBStore exports all of the certificates in the "MY" user store. This has the
advantage that it does not require user interaction with MMC. Use jbstore on
x64 platforms.

JBStore can be set to export from either the `CURRENT_USER\MY` store or the
`LOCAL_MACHINE\MY` store.  The default is `CURRENT_USER\MY`.

To export from the `LOCAL_MACHINE\MY` store:
`jbstore /computer <outfile> <password>`

To export from the `CURRENT_USER\MY` store:
`jbstore /user <outfile> <password>`

or

`jbstore <outfile> <password>`

Acknowledgements
----------------

Thank you to those who have performed testing or provided feedback. Especially
Andreas Klein for the jbcsp suggestions and Tom Aafloen for testing it on Vista
x64.

(c) 2007-2010 iSEC Partners (www.isecpartners.com)
