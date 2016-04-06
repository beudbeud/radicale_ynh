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

# This means all users starting with "admin" may read any collection
[admin]
user: ^admin.*$
collection: .*
permission: r

# This means all users may read and write any collection starting with public.
# We do so by just not testing against the user string.
[public]
user: .*
collection: ^public(/.+)?$
permission: rw

# A little more complex: give read access to users from a domain for all
# collections of all the users (ie. user@domain.tld can read domain/\*).
# [domain-wide-access]
# user: ^.+@(.+)\..+$
# collection: ^{0}/.+$
# permission: r

# Allow authenticated user to read all collections
[allow-everyone-read]
user: .+
collection: .*
permission: r

# Give write access to owners
[owner-write]
user: .+
collection: ^%(login)s/.+$
permission: w

# Partage public en lecture seule d'un agenda
#[public for readonly]
#user: .*
#collection: ^utilisateur/nom_calendrier*
#permission: r

# Partage public en lecture/écriture d'un agenda
#[public for read/write]
#user: .*
#collection: ^utilisateur/nom_calendrier*
#permission: rw

#[user1 can read and write user2/shared2]
#user: ^user1$
#collection: ^user2/shared2$
#permission: rw
