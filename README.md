# Sécurité réseau Installation du firewall pfSense
### 1. Installer pfSense : Configuration et Test de pfSense
  ![image](https://github.com/user-attachments/assets/79d2b35e-0786-47ad-aff8-1c760c5c65f6)
  
### 2. Pour s'assurer d'une configuration réseau valide permettant aux machines internes d'accéder à l'extérieur
- On va s'assurer que pfSense est configuré correctement avec une interface LAN (réseau interne) et une interface WAN (accès à Internet).

  ![image](https://github.com/user-attachments/assets/85b963a2-c3b7-4736-8268-29b1e672dfc4)

### 3. Tester que la machine client peut accéder à l'extérieur
- On teste la connectivité Internet depuis une machine interne en utilisant un ping vers une adresse externe (par exemple, `ping 8.8.8.8`)
![image](https://github.com/user-attachments/assets/7acb756f-cca3-4dff-95f6-8aff2a84b8a3)

4. Mettre en place une règle de filtrage réseau pour interdire à la machine client de sortir du réseau interne
Accédez à l'interface web de pfSense.

  pour cela on va dans Firewall -> Rules -> LAN.

Ajoutez une nouvelle règle pour bloquer le trafic sortant de la machine cliente :

    - Action : Block

    - Interface : LAN

    - Source : Adresse IP de la machine cliente

    - Destination : Any

    - Description : Bloquer le trafic sortant de la machine cliente

![image](https://github.com/user-attachments/assets/8f1ce9c2-eb82-496e-8b62-1680b73b67d1)

5. Vérifier que la machine client ne peut plus communiquer avec l'extérieur, mais que le poste d'administration peut encore communiquer avec l'extérieur
