# windows

-   [Chocolatey](https://chocolatey.org/), the software package manager for Windows.

    Open PowerShell as Administrator, and run:
    
        Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
    
    then run:
    
        choco feature enable -n allowGlobalConfirmation
        choco install git
        choco install nvm; nvm install latest; nvm use <latest>
    
    then close and re-open PowerShell as Administrator, and run:
    
        npm install -g windows-build-tools --vs2015
        npm config set python python2.7
    
    [hat tip](https://developer.bigcommerce.com/stencil-docs/installing-stencil-cli/installing-stencil)

-   [AutoHotkey](https://www.autohotkey.com/)

        choco install autohotkey

-   [ColorCop](http://colorcop.net/)

        choco install colorcop                  # possibly broken

-   [UnicodeInput.exe](https://www.fileformat.info/tool/unicodeinput/index.htm)
    -   Add this to your `Win+R shell:startup` folder.

-   [Cygwin](https://cygwin.com/)

        choco install cygwin cyg-get

-   [Google Chrome](https://www.google.com/chrome/)

-   [Firefox](https://www.mozilla.org/en-US/firefox/new/)

-   [A Ruler for Windows](https://www.arulerforwindows.com/)

-   [Foobar2000](https://www.foobar2000.org/)

        choco install foobar2000

-   [NVM for Windows](https://github.com/coreybutler/nvm-windows)

        choco install nvm

-   [Git for Windows](https://gitforwindows.org/)

        choco install git

-   [GitHub CLI for Windows](https://cli.github.com/)

        choco install gh

-   [XAMPP](https://www.apachefriends.org/index.html)

    -   `mkdir c:\xampp\apache\conf\local`
    
    -   append the following to `c:\xampp\apache\conf\httpd.conf`:

            Include conf/local/*.conf
    
    -   Open XAMPP as Administrator.
    
        -   Click the [X] next to Apache to set it up as a service.  It'll turn into a [check].
    
    -   Run Notepad as Administrator.
    
        -   Open c:\windows\system32\drivers\etc\hosts.
        
        -   Append entries like the following:
        
            ```
            
            ```
        
        -   Save.

-   [AWS CLI](https://aws.amazon.com/cli/)

        choco install awscli

-   Other things you can install:

        choco install less grep diffutils findutils nano patch awk Wget make gawk sed curl
