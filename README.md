# Development environment

## My development environment tools
- [Google Chrome](https://www.google.com/chrome/)
  - My favorites sites:
    - [Trello](https://trello.com/pt-BR)
    - [Notion](https://www.notion.so/)
    - [GitHub](https://github.com/)
    - [Replit](https://replit.com/)
    - [StackEdit](https://stackedit.io/)
    - [Figma](https://www.figma.com/)
    - [Excalidraw](https://excalidraw.com/)
  - My extensions:
    - [HTML5 Outliner](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo)
    - [Window Resizer](https://chrome.google.com/webstore/detail/window-resizer/kkelicaakdanhinjdeammmilcgefonfh)
    - [Meta Pixel Helper](https://chrome.google.com/webstore/detail/meta-pixel-helper/fdgfkebogiimcoedlicjlajpkdmockpc)
    - [Tag Assistant Legacy (by Google)](https://chrome.google.com/webstore/detail/tag-assistant-legacy-by-g/kejbdjndbnbjgmefkgdddjlbokphdefk?hl=pt-br)
    - [ColorZilla](https://chrome.google.com/webstore/detail/colorzilla/bhlhnicpbhignbdhedgjhgdocnmhomnp?gclid=EAIaIQobChMIxLmy96jt-wIVI0FIAB33mwoDEAAYASAAEgJrqPD_BwE)
- [XAMPP](https://www.apachefriends.org/download.html)
- [PHP](https://www.php.net/downloads)
- [Dbeaver](https://dbeaver.io/download/)
- [Draw.io - Desktop version](https://www.diagrams.net/)
- [Git](https://git-scm.com/)
- [MariaDB](https://mariadb.org/download/?t=mariadb&p=mariadb&r=10.11.2&os=windows&cpu=x86_64&pkg=msi&m=fder)
- [Emacs](https://www.gnu.org/software/emacs/)

## Setting up Emacs (Windows)
- Download Emacs [here](https://www.gnu.org/software/emacs/).
- Create a variable enviromment named `HOME` with your prefered path.
- Extract Emacs in **Program Files** folder in `C:\`.
- Download and paste **.emacs.d** folder inside your `HOME` path.            

## Setting up a web server (Windows)
- Download and install [XAMPP](https://www.apachefriends.org/download.html)
- Add [Xdebug](https://xdebug.org/) extension to XAMPP:
  - Start Apache on XAMPP and access http://localhost/dashboard/ in your browser.
  - Go to the PHPInfo page and select and copy all page.
  - Go to [Xdebug Installation Wizard](https://xdebug.org/wizard), paste the copied page in textarea and click on **Analyse my phpinfo() output** button to get the correct Xdebug file.
  - Follow the given instructions
- Install an SSL certificate to use **https**:
  - Go to `C:\xampp\apache` directory and create a `domains.ext` file.
  - Copy the following text inside the `domain.ext` file:
	```
	authorityKeyIdentifier=keyid,issuer  
	basicConstraints=CA:FALSE  
	keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment  
	subjectAltName = @alt_names  
	[alt_names]  
	DNS.1 = localhost  
	DNS.2 = www.localhost
	```
  - Go to `C:\xampp\apache` and open the `makecert.bat` file with a text editor.
  - At the end of `...server.key -days 365` line add the following command:
    - `-sha256 -extfile domains.ext`  
  - Execute the `makecert.bat` file, answer just the following questions and skip the rest with the RETURN button:
    - `Enter PEM pass phrase:` (a secure password)
    - `Verifying - Enter PEM pass phrase:` (retype the password)
    - `Country Name (2 letter code) [AU]:` (your country code)
    - `Common Name (e.g. server FQDN or YOUR name) []:` (answer with **localhost**)
    - `Enter pass phrase for privkey.pem:` (your password)
  - Go to `C:\xampp\apache\conf\ssl.crt` and execute the `.crt` file.
    - In the **Certificate Store** section select the **Place all certificates in the following store** and choose **Trusted Root Certification Authorities**

