# DEVICES
Questa è una lista (in continuo aggiornamento) dei dispositivi smart che utilizzo quotidianamente.
Sono stati tutti integrati all'interno di Home Assistant, mediante le configurazioni che trovate in questa repository.
Utilizzo 2 Sistemi Home Assistant nella mia abitazione in quanto mi andavano in conflitto la penna che gestisce la rete Z-Wave e la rete Zigbee sulla stessa configurazione.
La configurazione principale legge i dati e comunica con la seconda attraverso il plugin [remote_homeassistant].

# CONFIGURAZIONE PRINCIPALE
Utilizzo come server per la mia domotica un [INTEL NUC7I3BNH] con a bordo 4+8= 12 GB di Ram, [120 Gb di SSD M2 Samsung].
Il sistema operativo è [Proxmox 6] sul quale girano come Virtual Machine:
 - un sistema Linux [Debian] con [Docker], su cui tra gli altri gira il container ufficiale di [Home Assistant per amd64].
 - un container [Ubuntu] con [Pi-Hole] installato seguendo [questa guida].
 Al NUC ho collegato:
  - una [Aeotec USB Z-Stick] che gestisce tutta la rete Z-Wave di casa.
  - una [SanDisk Ultra Fit] da 128 GB sulla quale conservo i backup dei container e delle VM di Proxmox generati in modo automatico dal sistema.


# CONFIGURAZIONE SECONDARIA
Utilizzo come postazione secondaria un [Raspberry Pi 3 Model B] con installato a bordo Hassio come da [guida ufficiale].
Al dispositivo ho collegato:
 - una [Conbee 2] che gestisce tutta la rete Zigbee relativa alla domotica in abbinato all' add-on ufficiale DeConz.
 - un [powerbank Zendure con tecnologia Passthrough] che svolge la funzione di UPS per questa configurazione secondaria.

[INTEL NUC7I3BNH]: <https://amzn.to/2TTdeDw>
[120 Gb di SSD M2 Samsung]: <https://amzn.to/2HDHZWw>
[Proxmox]: <https://www.proxmox.com/en/>
[Debian]: <https://www.debian.org/>
[Docker]: <https://www.docker.com/>
[Home Assistant per amd64]: <https://diyfuturism.com/index.php/2018/03/20/pi-to-nuc-part-1-migrating-hass-io-to-a-virtual-machine-proxmox-docker/>
[Ubuntu]: <https://www.ubuntu-it.org/>
[Pi-Hole]: <https://pi-hole.net/>
[questa guida]: <https://www.linuxincluded.com/install-pi-hole-on-ubuntu/>
[remote_homeassistant]: <https://github.com/lukas-hetzenecker/home-assistant-remote>
[Raspberry Pi 3 Model B]: <https://amzn.to/2Fvos7u>
[guida ufficiale]: <https://www.home-assistant.io/hassio/installation/>
[Conbee 2]: <https://amzn.to/2QXWJSx>
[powerbank Zendure con tecnologia Passthrough]: <https://amzn.to/2s1vaiw>
[Aeotec USB Z-Stick]: <https://amzn.to/2tzeiAj>
[SanDisk Ultra Fit]: <https://amzn.to/2ukIDmi>
