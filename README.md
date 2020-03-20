# IP Redirect
![GitHub](https://img.shields.io/github/license/dynamiccookies/IP-Redirect?style=for-the-badge)
![GitHub file size in bytes](https://img.shields.io/github/size/dynamiccookies/IP-Redirect/index.php?style=for-the-badge)

Script that redirects to the internal or external IP address of an application based on public IP of the client.


## Use Case
This script was created to accommodate applications such as Lidarr, Sonarr, Radarr, SickBeard, CouchPotato, and SABnzbd. Placing this script on a subdomain, such as lidarr.example.com, or a subfolder, such as example.com/lidarr, will redirect the client to the internal or external IP address of the app based on the client's current location. However, it can be used with any application or site that may require internal access while on the network but external access while off of it.


## Configuration
The following section of code is where you will need to configure your variables.<br>Examples are in bold.
<pre>
//<strong>My Application Name</strong>

//********************************************************************
//*********************Enter Your Variables Here**********************
//********************************************************************

//Internal IP Address to the Server
$internalIP     = '<strong>192.168.1.2</strong>';

//Internal Port to the Application
$internalPort   = '<strong>1234</strong>';

//External IP Address to the Server (ISP)
$externalIP     = '<strong>200.1.2.3</strong>';

//External Port to the Application (default = $internalPort)
$externalPort   = <strong>$internalPort</strong>;

//Does this application use https?
$https          = <strong>false</strong>;
</pre>


## Variable Definitions
**`$internalIP`**:<br>
Internal IP address of the server. This IP address can only be reached from inside the network.

**`$internalPort`**:<br>
Internal port number for the application. **If port 80, this can be left blank.**

**`$externalIP`**:<br>
External public IP address assigned by the internet service provider (ISP). From inside the network, use [https://www.whatismyip.com/](https://www.whatismyip.com/) to find the IP address. <br>**Note:** This IP address can change if you  do not subscribe to a static IP address from your ISP. Be prepared to update this in the future.

**`$externalPort`**:<br>
Port number opened on the router to allow traffic for this application to travel through. It does not need to be the same as the internal port number; however, this script assumes the internal and external port numbers are the same by setting `$externalPort` equal to `$internalPort` by default. If they are not, simply replace `$internalPort` with the number.

**`$https`**:<br>
Boolean (true/false) variable to determine whether `http` or `https` should be used. It is assumed `https` is not being used by default. If it is, change the word `false` to `true`.


## License

This project uses the following license: [Unlicense](LICENSE).
