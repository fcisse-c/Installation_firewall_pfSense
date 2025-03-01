# Sécurité réseau Installation du firewall pfSense
## Configuration et Test de pfSense

### 1. Pour s'assurer d'une configuration réseau valide permettant aux machines internes d'accéder à l'extérieur
- On va s'assurer que pfSense est configuré correctement avec une interface LAN (réseau interne) et une interface WAN (accès à Internet).
  ![image](https://github.com/user-attachments/assets/79d2b35e-0786-47ad-aff8-1c760c5c65f6)

- On teste la connectivité Internet depuis une machine interne en utilisant un ping vers une adresse externe (par exemple, `ping 8.8.8.8`)


### 2. Tester que la machine client peut accéder à l'extérieur
- Depuis la machine cliente, ouvrez l'invite de commande ou le terminal.
- Exécutez la commande suivante pour vérifier la connectivité :
  ```bash
  ping 8.8.8.8

![image](https://github.com/user-attachments/assets/64d08e8c-5981-48aa-bfb1-762008ea844b)


3. Mettre en place une règle de filtrage réseau pour interdire à la machine client de sortir du réseau interne
Accédez à l'interface web de pfSense.

  pour cela on va dans Firewall -> Rules -> LAN.

Ajoutez une nouvelle règle pour bloquer le trafic sortant de la machine cliente :

    - Action : Block

    - Interface : LAN

    - Source : Adresse IP de la machine cliente

    - Destination : Any

    - Description : Bloquer le trafic sortant de la machine cliente
