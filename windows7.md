# Life in Windows 7 in 2021

Windows 10 is minimalist trash that performs poorly on older hardware.

Windows 7 has useful window decorations, and works fine on older
hardware.  You can even use the Windows Classic theme and set your
background to solid color `#`.

Microsoft doesn't update Windows 7 anymore.  You'll have to deal with
some concomitant issues here and there.

## Get a good browser.

-  [Google Chrome][chrome]
-  [Firefox Browser][firefox]

## Get an antivirus.

Windows 7 doesn't come with Windows Defender like Windows 10 does.
You absolutely need an antivirus program if you want to run Windows 7.
[Kaspersky Security Cloud][kaspersky] seems to work fine, seems to
have all the features you need without paying for a premium version,
and seems to not slow your computer down too much.

You don't want McAfee.

## Update your certificate store.

Windows 7 won't do this automatically, so you'll have to do it on your
own.  While Firefox has its own certificate store, Google Chrome relies
on the one provided by the OS.

Your SSL/TLS root certificates are located in [a text file][roots].
It's a large PEM file that contains multiple certificates.  You'll
need to split it into individual files, somehow, run an administrave
shell, and install each one using:

```
certutil -addstore -enterprise -f Root cert1.pem
certutil -addstore -enterprise -f Root cert2.pem
...
```

To confirm that your security store is up-to-date, visit
[HowToGeek][howtogeek] in Google Chrome.

## Update to Service Pack 1.

1.  [Windows 7 Service Pack 1][sp1]

## Update your PowerShell.

You'll need to install SP1 to do this.

-   [Universal C Runtime][ucrun], select the applicable `Windows6.1` version.
-   [Windows Management Framework][wmf] 4.0 or later (5.1 = KB3191566)
-   [PowerShell][ps]

## Install Chocolatey.

You'll need to update to SP1, and install PowerShell as above, to do this.

-   [Chocolatey][choco]

## Install some Chocolatey packages.

You probably want to run the following:

```
choco feature enable -n allowGlobalConfirmation
```

Then here's a list of packages I install:

```
choco install less wget curl git gh emacs rsync openssh autohotkey
choco install diffutils findutils awk sed nano patch gawk
```

`gh` is the GitHub CLI for Windows.  You use it to work with GitHub
repositories.

## Also Install These:

-   [Color Cop][colorcop] (fails to install in choco)

## Additional Issues That Seem Impossible to Solve

-   Some fonts in Google Fonts will not display in Windows 7.
    Not in Google Chrome; not even in Firefox.

## Links

[ccadb]: https://www.ccadb.org/
[roots]: https://ccadb-public.secure.force.com/mozilla/IncludedRootsPEMTxt?TrustBitsInclude=Websites
[colorcop]: http://colorcop.net/
[chrome]: https://www.google.com/chrome/
[firefox]: https://www.mozilla.org/en-US/firefox/new/
[kaspersky]: https://usa.kaspersky.com/security-cloud
[howtogeek]: https://www.howtogeek.com/
[ucrun]: https://aka.ms/pscore6-prereq
[ps]: https://aka.ms/powershell-release?tag=stable
[sp1]: https://www.catalog.update.microsoft.com/Search.aspx?q=KB976932
[wmf]: https://www.microsoft.com/en-us/download/details.aspx?id=54616
[ps]: https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7.1
[choco]: https://chocolatey.org/

