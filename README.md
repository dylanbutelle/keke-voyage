# Keke Voyage

## Dictionnaire de données

---

|NOM             |TYPE                           |DESIGNATION                  |
|----------------|-------------------------------|-----------------------------|
|ID_Client       |Alphanumérique                 |Identifiant du client                 |
|Nom             |Alphanumérique                 |Nom du client                |
|Prénom          |Alphanumérique                 |Prénom du client             |
|Date de naissance             |Date                           |Date de naissance du client  |
|Email           |Alphanumérique                 |Adresse mail du client       |
|Numéro de téléphone       |Alphanumérique                 |Numéro de téléphone du client|
|Id_Passager      |Alphanumérique                 |Identifiant du passager|
|////////////////|///////////////////////////////|/////////////////////////////|
|ID_Passager      |Alphanumérique                 |Identifiant du passager                 |
|Nom             |Alphanumérique                 |Nom du passager                |
|Prénom          |Alphanumérique                 |Prénom du passager             |
|Id_Vol             |Alphanumérique                           |Identifiant du vol  |
|Numéro de passeport           |Alphanumérique                 |Numéro de passeport du passager       |
|Id_Client    |Alphanumérique                 |Identifiant du client ayant réservé le vol|
|////////////////|///////////////////////////////|/////////////////////////////|
|ID_Compagnie    |Alphanumérique|Identifiant de la compagnie aérienne|
|Nom             |Alphanumérique|Nom de la compagnie aérienne|
|////////////////|///////////////////////////////|/////////////////////////////|
|ID_vol          |Alphanumérique|Identifiant du vol|
|Compagnie       |Alphanumérique|Identifiant de la compagnie assurant le vol|
|Date de départ  |Datetime|Date et heure de départ du vol|
|Aéroport de départ|Alphanumérique|Identifiant de l'aéroport de départ du vol|
|Aéroport d'arrivée|Alphanumérique|Identifiant de l'aéroport d'arrivée du vol|
|Destination|Alphanumérique|Destination du vol|
|Ouvrir_vol      |Boolean|Ouverture de la réservation par la compagnie|
|Fermer_vol      |Boolean|Fermeture de la réservation par la compagnie|
|Escale          |Alphanumérique|Identifiant de l'aéroport de l'escale|
|////////////////|///////////////////////////////|/////////////////////////////|
|ID_Aéroport     |Alphanumérique|Identifiant de l'aéroport|
|Villes desservies|Alphanumérique|Villes desservies par l'aéroport|
|Vols au départ  |Alphanumérique|Identifiant des vols au départ de l'aéroport|
|Vols à l'arrivée|Alphanumérique|Identifiant des vols à l'arrivée de l'aéroport|
|////////////////|///////////////////////////////|/////////////////////////////|
|ID_Escale       |Alphanumérique|Identifiant de l'aéroport de l'escale du vol|
|Heure d'arrivée  |Time|Heure d'arrivée du vol|
|Heure de départ  |Time|Heure de départ du vol|

---

## Régles de gestion

### Client

* Un client doit renseigner son nom, son prénom, sa date de naissance, son email et son numéro de téléphone.

* Un client peut réserver plusieurs billets. Il peut également réserver pour une tier personne.

* Lors d'une réservation, un client se voit attribué un passager.

### Passager

* Un passager a un nom, un prénom, un numéro de passeport.

* Le passager peut être un client. 

* On attribut, lors de la réservation, l'identifiant unique du client qui a réservé.

* Le passager lui voit attribué un numéro de vol lors de la réservation.

### Compagnie

* La compagnie possède un nom et un identifiant.

* Les vols depende des compagnies, chaque compagnie possède ces propres vols.

### Vol

* Un vol existe seulement lorsque la compagnie l'assure.

* Un vol doit avoir une date et heure de départ, une date et heure d'arrivée, un aéroport de départ et d'arrivée, un nom de compagnie, une destination et les escales s'il y en a.

* Si le client reçoit le billet, cela veut dire que le vol a été créé par la compagnie et qu'il est disponible (ouvrirVol = true). La compagnie peut toujours fermer le vol (fermerVol = true) dans ce cas le vol n'est plus disponible et le programme avertira automatiquement le client que son vol (identifié grâce à son ID) est annulé. 

* Le vol dépend de la compagnie, il est créé par la compagnie et peut être aussi supprimé. 

### Aéroport 

* Un aéroport peut avoir plusieurs vols. 

* Un aéroport dessert plusieurs villes.

### Escale 

* Une escale est un héritage de l'aéroport au vu des escales qui peuvent pas être des destinations finales.

* L'escale possède une heure d'arrivée, une heure de départ et un identifiant.

---

