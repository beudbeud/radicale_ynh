# Radicale

Radicale est un serveur de calendrier et de contact CalDAV/CardDAV. Il ne dispose pas d'une interface d'administration.

Radicale est installé par défaut avec le client web InfCloud qui permettra de visualiser et de modifier vos calendriers et carnets d'adresses.

Pour connecter un autre client au serveur radicale, il faut renseigner ces adresses:

## Collection CalDAV/CardDAV complète d'un utilisateur:
URL : https://domain.tld/path/user/

Exemple : https://example.org/radicale/moi/

## Pour connecter un calendrier en particulier:
URL : https://domain.tld/path/user/calendar.ics/

Exemple : https://example.org/radicale/moi/calendar.ics/

### ics et caldav indifféremment???

## Pour connecter un carnet d'adresses en particulier:
URL : https://domain.tld/path/user/AddressBook.vcf/

Exemple : https://example.org/radicale/moi/AddressBook.vcf/

## Créer un nouveau calendrier ou un nouveau carnet d'adresses
Créer un nouveau calendrier ou un nouveau carnet d'adresses est très simple avec radicale, il suffit d'y accéder! Radicale créera tout nouveau calendrier ou carnet d'adresses inexistant si vous tentez d'y accéder.

Il suffit donc de se connecter (comme précédemment) à un calendrier ou un carnet d'adresses inexistant pour le créer.
Cela peux être fait simplement avec un navigateur, pour le voir apparaitre dans une collection déjà connectée à un client.

---


Qu'est-ce que je voulais ajouter?
Les règles de partage et de droits!
