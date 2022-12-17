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


### Before starting

This service is not free today, it requires a monthly subscription to use. (More information in our discord -- https://discord.com/invite/yRSs48FewF)


## Example
<div align="center">
  <h2>In Game</h2>
  
  <img src="https://cdn.discordapp.com/attachments/754887805200760882/1036741507375448184/sa-mp-087.png"></img>
   
  <h2>Discord Channel</h2>
  
  <h3>Simple Message</h3>
  <img src="https://cdn.discordapp.com/attachments/754887805200760882/1036740893585191014/unknown.png"></img>
  
  <p>Note: <strong>the username and image (avatar) would change in a future</strong> (Custom)</p>
  
  <h3>Message Embed</h3>
  <img src="https://cdn.discordapp.com/attachments/754887805200760882/1053811792410853479/image.png"></img>+
  
  <p>Note: <strong>the username in message embed is the same as the webhook</strong> (Image can be changed in a futures releases)</p>

</div>


<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Dependencies

* None

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Getting Started

### Installation

1. Place the `API.amx` file in your filterscripts folder.
2. Add on server startup in `server.cfg`

2.1 ```filterscripts API```

3. Pay the monthly subscription to enable the channel(s)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Syntax ES: ``SendDiscordMessage(ID Del servicio, Token de usuario, playerid, Contenido del mensaje)``

Syntax ES: ``SendDiscordEmbed(ID Del servicio, Token de usuario, playerid, Titulo del embed, Información (Label 1), Mensaje)``

Syntax EN: ``SendDiscordMessage(Service ID, User Token, playerid, Message content)``

Syntax EN: ``SendDiscordEmbed(Service ID, User Token, playerid, Embed title, Label 1 content, Message content)``

Example:
```c
public OnPlayerDeath(playerid, killerid, reason)
{
    new Name[MAX_PLAYER_NAME], Name2[MAX_PLAYER_NAME], string[128];

    GetPlayerName(playerid, Name, MAX_PLAYER_NAME);
    GetPlayerName(killerid, Name2, MAX_PLAYER_NAME);

    format(string, sizeof string, "The player %s died in hands of %s", Name, Name2);
    
    CallRemoteFunction("SendDiscordMessage", "dsds", 1, "secrettoken", playerid, string);

    return 1;
}
```


<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Error Code(s)

These codes allow reporting in case of errors

ES:

```CODE:

1 - Discord App error (API Probablemente caída / Fuera de servicio)

2 - Discord webhook inválido

3 - Cliente / Servicio no encontrado (Servicio no contratado o activo)

404 - Datos incorrectos (Vacíos o nulos) / Error de FS, Actualiza al último release o pide ayuda a soporte
```

EN:

```
CODE:

1 - Discord App error (API System down)

2 - Invalid Discord webhook

3 - Client / Service not found (Service not contracted or active)

404 - Incorrect data (Empty or null) / FS error, Update to the latest release or ask support for help
```

Ex:

<img src="https://cdn.discordapp.com/attachments/754887805200760882/1053819574451195914/error.JPG" width=80%></img>

## Contact & More

© BryanM (Bryan Miltoner)


`Discord` -->

<a href="https://discord.gg/yRSs48FewF" target="_blank">
  <img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/625e5fcef7ab80b8c1fe559e_Discord-Logo-Color.png" width=8%></img>
</a>

<h4>All sections of this document have been created with a template (Credits to their creators)</h4>

<p align="right">(<a href="#readme-top">back to top</a>)</p>
