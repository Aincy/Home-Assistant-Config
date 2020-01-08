# CONTAINER PIHOLE

Creare un LXC Debian 10 su Proxmox, nel mio caso ho dedicato 2 CPU, 2 Gb di Ram e 16 Gb di disco.
Una volta avviato il container prenotare un IP statico interno alla nostra rete e aprire la console:

> apt update -y && apt upgrade -y && reboot
> apt install -y curl
> curl -sSL https://install.pi-hole.net | bash
