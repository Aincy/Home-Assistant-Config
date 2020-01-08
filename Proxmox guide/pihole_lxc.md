# CONTAINER PIHOLE

Creare un LXC Debian 10 su Proxmox, nel mio caso ho dedicato 2 CPU, 2 Gb di Ram e 16 Gb di disco.
Una volta avviato il container prenotare un IP statico interno alla nostra rete (è fondamentale nell'utilizzo di pihole!) e aprire la console.

### INSTALLAZIONE

> apt update -y && apt upgrade -y && reboot

> apt install -y curl

> curl -sSL https://install.pi-hole.net | bash

### CAMBIO PASSWORD
> pihole -a -p

### BLACKLIST
Di fondamentale importanza è la blacklist da dove il nostro pihole capisce cosa bloccare. Prendendo spunto dal [blog di Andrea Draghetti] ho inserito questa blacklist:

> https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts
> https://mirror1.malwaredomains.com/files/justdomains
> https://zeustracker.abuse.ch/blocklist.php?download=domainblocklist
> https://www.squidblacklist.org/downloads/dg-ads.acl
> https://www.squidblacklist.org/downloads/dg-malicious.acl
> https://phishing.army/download/phishing_army_blocklist_extended.txt
> https://raw.githubusercontent.com/lightswitch05/hosts/master/ads-and-tracking.txt
> https://raw.githubusercontent.com/hoshsadiq/adblock-nocoin-list/maste

Per bloccare le pubblicità di Youtube invece prendendo spunto da [Domology 2.0] ho inserito da poco nella Blacklist:
> (^r[[:digit:]]+(.|-+)[[:alnum:]]+-+[[:alnum:]]+-+[[:alnum:]]+.)(googlevideo|gvt1).com$

> ^(.+[-.])??adse?rv(er?|ice)?s?[0-9][-.]

> ^(.+[-.])??m?ad[sxv]?[0-9][-.]

> ^adim(age|g)s?[0-9][-.]

> ^adtrack(er|ing)?[0-9][-.]

> ^advert(s|is(ing|ements?))?[0-9][-_.]

> ^aff(iliat(es?|ion))?[-.]

> ^analytics?[-.]

> ^banners?[-.]

> ^beacons?[0-9][-.]

> ^count(ers?)?[0-9][-.] ^pixels?[-.]

> ^stat(s|istics)?[0-9][-.]

> ^telemetry[-.]

> ^track(ers?|ing)?[0-9]*[-.]

> ^traff(ic)?[-.]

### Per aggiornare il nostro Pihole da console del container:
> pihole -up

### CONFIGURAZIONE
E' necessario per far funzionare il nostro nuovo ad-blocker inserire come DNS sul nostro router l'ip che abbiamo prenotato per il nostro Pihole.

### CONSIGLIO
Ho preso come abitudine inserire in whitelist i siti che più gradisco sul web in modo da supportarli con le loro pubblicità. Pihole deve essere solo uno strumento di "difesa" dalle pubblicità sgradevoli e fastidiose che alcuni portali web inseriscono in modo da migliorare la nostra navigazione web, ma non ucciderla eliminando gli introiti, che seppur minuscoli, finanziano le risorse che noi utilizziamo su internet.

[blog di Andrea Draghetti]: <https://www.andreadraghetti.it/block-list-e-white-list-per-pi-hole-e-ad-blocker/>
[Domology 2.0]:<https://domology.es/bloquear-anuncios-de-youtube-con-pi-hole/>
