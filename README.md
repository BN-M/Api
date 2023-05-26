<a name="readme-top"></a>

<br />

<div align="center">
  <a href="https://github.com/BN-M/Discord-SAMP-API">
    <img src="https://icon-library.com/images/pawn-icon/pawn-icon-12.jpg" alt="Logo" width="80" height="80"></img>
  </a>

  <h2>SAMP-API</h2>

  <h3>Public Beta 1st Release - (May, Friday 26 2023)</h3>
  
  <br />
  
  <p>ES: Nuestra API se encarga de comunicar tu servidor de SA-MP con tu entorno de desarrollo.</p>
  <p>EN: Our API is in charge of communicating your SA-MP server with your development environment.</p>
	
  <br />
  <a href="https://github.com/BN-M/Discord-SAMP-API"><strong>Explore the docs »</strong></a>
  <br />
  <br />
  <a href="https://github.com/BN-M/Discord-SAMP-API/releases">Releases ^</a>
</div>

<br />

  <h4>Announcements</h4>
  
<ul>26/05/23
  <li>ES: Se abre al público la v1.0, Estaremos al tanto de errores o inconvenientes respecto a la API y FS recuerden que estamos en BETA.</li>
  <li>EN: v1.0 is released, we will be aware of errors or inconveniences remember the API and FS still in BETA.</li>
</ul>

<br />

### Introduction
<div align="center">
  <h2>What is it about</h2>
   
  <p>Currently our API develops communication functions (Environment -> Server).</p>
	
  <h3>Current Version (1.0 BETA)</h3>
  
  <h4>Available functions</h4>
  
  <p>· Call of remote functions (Public's - Without parameters)</p>

  <p>· Send RCON commands</p>
	
<br />
	
  <img src="https://cdn.discordapp.com/attachments/754887805200760882/1105703663743279164/image.png"></img>

<br />
	
  <h3>Information  (Requests)</h3>
  
  <p>ALL: Server & Client side</p>
  
  <table>
  <tr>
    <th>Path</th>
    <th>Method</th>
    <th>Params (*)</th>
    <th>Supported data</th>
    <th>Mode</th>
  </tr>
	
  <tr>
    <td>neshy-rp.com/api/Gateway/Requests/</td>
    <td>GET</td>
    <td>[string] => token</td>
    <td>GET</td>
    <td>Client Only</td>
  </tr>
	
  <tr>
    <td>neshy-rp.com/api/Gateway/Requests/</td>
    <td>POST</td>
    <td>[string] => token - [string] => funcname</td>
    <td>POST - HEADERS</td>
    <td>ALL</td>
  </tr>
	
  <tr>
    <td>neshy-rp.com/api/Gateway/Requests/</td>
    <td>PUT</td>
    <td>[string] => token - [int] => id - [string] => order</td>
    <td>POST - HEADERS</td>
    <td>ALL</td>
  </tr>

  <tr>
    <td>neshy-rp.com/api/Gateway/Requests/</td>
    <td>DELETE</td>
    <td>[string] => token - [int] => id</td>
    <td>POST - HEADERS</td>
    <td>ALL</td>
  </tr>
	
</table>

</div>


<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Dependencies

* None

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Installation

1. Place the `API.amx` file in your filterscripts folder.
2. Add on server startup in `server.cfg`

2.1 ```filterscripts API```

3. Done

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- USAGE EXAMPLES -->
## Getting started

<p>Our API uses a token system to identify clients (Server side and client side), so don't share it with anyone</p>

<h3>Function's</h3>

<p><strong>GetApiKey()</strong> - Generate a new token for use, it calls the public function -> <strong>OnApiGenerateToken(const token[])</strong> Which receives as a parameter the generated token</p>

<p><strong>CheckApiRequest(const token[])</strong> - It is in charge of reviewing orders registered in the API with the token</p>


<h3>Server side</h3>

```c

new API_KEY[17];

public OnGamemodeInit()
{
    CallRemoteFunction("GetApiKey", ""); // Generate token
    return 1;
}

forward OnApiGenerateToken(const token[]); // Receive token
public OnApiGenerateToken(const token[])
{
	format(API_KEY, sizeof API_KEY, token);

	SetTimer("ApiTimer", 5000, true); // Every 5 seconds check if there are pending orders

	return 1;
}

forward ApiTimer();
public ApiTimer()
{
	CallRemoteFunction("CheckApiRequest", "s", API_KEY);

	return 1;
}

```

<h3>Client side (global - functions)</h3>

```
POST /HTTP/1.1
Host: API/EXAMPLE
Content-Type: application/x-www-form-urlencoded
Content-Length: 29

token=mytoken&funcname=myfunc
```

<h4>In about 5 seconds on sa-mp server, the public function (myfunc) should be called</h4>

<h3>Client side (global - rcon)</h3>

```
POST /HTTP/1.1
Host: API/EXAMPLE
Content-Type: application/x-www-form-urlencoded
Content-Length: 40

token=mytoken&funcname=rcon password 123
```

<h4>In about 5 seconds on sa-mp server, the password will be set to 123 via RCON command</h4>

<p><strong>Note:</strong> The method doesn`t need the rcon password because is called natively from the sa-mp server (FS)</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Error Codes

<h3>These codes allow reporting in case of errors</h3>

<p>Server side</p>

```
1..6 - WHILE RECEIVING PACKET / WHILE GENERATING TOKEN (API request error)

200 - token (INVALID / EXPIRED TOKEN)
```

<p>Client side</p>

```
200 - token (INVALID TOKEN)

200 - id (REQUEST ID NOT EXITS / ALREADY SEND TO SERVER)

200 - empty (REQUEST'S QUEUE IS EMPTY)

400 - bad request's (API REQUEST SYNTAX ERROR)
```

## Contact & More

<p>© BryanM - BryanM#0871 (Discord)</p>

<p><strong>Any review will be welcome (Respect above all), I'm also new in github so any hazing forgive me hehe.</strong> Thanks to neshy (Web-core host)</p>

<p>All sections of this document have been created with a template (Credits to their creators)</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
