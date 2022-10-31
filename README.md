<a name="readme-top"></a>

<!-- PROJECT LOGO -->

<br />

<div align="center">
  <a href="https://github.com/BN-M/Discord-SAMP-API">
    <img src="https://icon-library.com/images/pawn-icon/pawn-icon-12.jpg" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">Discord  SAMP-API</h3>

  <p align="center">
    ES: 
    Nuestra API se encarga de comunicar discord con tu servidor de manera sencilla, Nuestra meta es ofrecer un servicio facil de usar y efectivo, Por un precio justo.
    <br />
    <br />
    EN: 
    Our API is in charge of communicating discord with your server in a simple way, our goal is to offer an easy to use and effective service, For a fair price.
    </p>
    <br />
    <a href="https://github.com/BN-M/Discord-SAMP-API"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/BN-M/Discord-SAMP-API/releases">1st Release</a>
</div>


### before starting

This service is not free today, it requires a monthly subscription to use. (More information in our discord)


## Example
<div align="center">
  <h2>In Game</h2>
  
  <img src="https://cdn.discordapp.com/attachments/754887805200760882/1036741507375448184/sa-mp-087.png"></img>
   
  <h2>Discord Channel</h2>
  <img src="https://cdn.discordapp.com/attachments/754887805200760882/1036740893585191014/unknown.png"></img>
  
  <p>Note: <strong>the username and image (avatar) would change in a future</strong> (Custom)</p>

</div>


<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Dependencies

* a_samp

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Getting Started

Note: The Discord-Webhook.inc is a bonus file, It contains a function (stock) to facilitate the call of the main function (By CallRemoteFunction) it is not necessary to download it and you can create your own function following the syntax.

### Installation

1. Place the `discord.amx` file in your filterscripts folder.
2. Add on server startup in `server.cfg`

2.1 ```filterscripts discord```

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Syntax ES: ``NativeWebhook(menciones = 0, skin = 0, const nombre[] = Nickname (Discord), const token[] = Token del usuario (cliente), const mensaje[] = Mensaje)``

Syntax EN: ``NativeWebhook(everyone = 0, skin = 0, const nombre[] = Username (Discord), const token[] = Client Token, const mensaje[] = Message)``

Example (Only FS - Native):
```c
public OnPlayerDeath(playerid, killerid, reason)
{
    new Name[MAX_PLAYER_NAME], Name2[MAX_PLAYER_NAME], string[128];

    GetPlayerName(playerid, Name, MAX_PLAYER_NAME);
    GetPlayerName(killerid, Name2, MAX_PLAYER_NAME);

    format(string, sizeof string, "The player %s died in hands of %s", Name, Name2);

    CallRemoteFunction("NativeWebhook", "ddsss", 0, 0, "My server", "secrettoken", string);

    return 1;
}
```

Example (Using the .inc file):
```c
public OnPlayerDeath(playerid, killerid, reason)
{
    new Name[MAX_PLAYER_NAME], Name2[MAX_PLAYER_NAME], string[128];

    GetPlayerName(playerid, Name, MAX_PLAYER_NAME);
    GetPlayerName(killerid, Name2, MAX_PLAYER_NAME);

    format(string, sizeof string, "The player %s died in hands of %s", Name, Name2);

    MensajeWebhook("My server", "secrettoken", string, 0, 0);

    return 1;
}
```


<h3>Both methods have the same result.</h3>

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Contact & More

© BryanM (Bryan Miltoner) - parzival210 (Parzival)

`Discord` -->

<a href="https://discord.gg/yRSs48FewF" target="_blank">
  <img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/625e5fcef7ab80b8c1fe559e_Discord-Logo-Color.png" width=8%></img>
</a>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
