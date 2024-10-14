# Découpage de réseaux IP

## Généralités
Une société fictive a 4 pôles informatiques. Le réseau est en 172.16.1.0/24.
Découper ce réseau de 2 manières, symétrique et asymétrique, pour que chaque pôle ci-dessous puissent avoir assez d'adresse pour chaque équipement.

  * **Sous-réseau 1** : _Le Pôle informatique (6 bureaux, environ 50 équipements au total)_
  * **Sous-réseau 2** : _Le Pôle développement (6 bureaux, environ 12 équipements au total)_
  * **Sous-réseau 3** : _Le Pôle Administratif (4 bureaux, environ 20 équipements au total)_
  * **Sous-réseau 4** : _Le Pôle Technicien (4 bureaux, environ 15 équipements au total)_

## Découpage symétrique
Chaque sous-réseau seront de taille asymétrique et devra au moins accueillir 50 équipements.
### Calcul du CIDR
On calcul le CIDR en prenant le chiffre de la puissance, soit : 2^6 = 64, _cela permettra d'accueillir les 50 équipements_.<br>
Ensuite, il faut enlever le nombre de bits hôte, soit : 64-6 = 58, cela donne un CIDR de /58.
### Découpage des sous-réseaux
  * Sous-réseau 1

Adresse de réseau | Adresse de début | Adresse de fin | Adresse de broadcast
--- | --- | --- | ---
172.16.1.0/58 | 172.16.1.1 | 172.16.1.62 | 172.16.1.63

  * Sous-réseau 2

Adresse de réseau | Adresse de début | Adresse de fin | Adresse de broadcast
--- | --- | --- | ---
172.16.1./58 | 172.16.1.1 | 172.16.1.62 | 172.16.1.63

  * Sous-réseau 3

Adresse de réseau | Adresse de début | Adresse de fin | Adresse de broadcast
--- | --- | --- | ---
172.16.1.0/58 | 172.16.1.1 | 172.16.1.62 | 172.16.1.63

  * Sous-réseau 4

Adresse de réseau | Adresse de début | Adresse de fin | Adresse de broadcast
--- | --- | --- | ---
172.16.1.0/58 | 172.16.1.1 | 172.16.1.62 | 172.16.1.63
