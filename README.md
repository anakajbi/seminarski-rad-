# seminarski-rad-


Ovaj kod stvara jednostavnu "chatroom" aplikaciju koja se povezuje na Scaledrone API
gdje korisnici mogu razgovarati i slati poruke u javnu sobu "observable-room".

Ovdje su ključne stvari koje se događaju u kodu:

Postavlja se konstanta "CLIENT_ID" koja predstavlja ID klijenta koji se koristi za povezivanje sa Scaledrone API-em.


Stvara se objekt "drone" korištenjem konstruktora "ScaleDrone" koji prima "CLIENT_ID" i neke podatke o klijentu, uključujući ime i boju.

Postavlja se prazan niz "members" koji će se koristiti za praćenje članova u sobi.

Postavlja se slušač događaja "open" na "drone" objektu koji se poziva kada se uspješno povežemo s Scaledrone API-em.


Kada se ovo dogodi, "drone" pretplaćuje sobu "observable-room" i postavlja različite slušače događaja za događaje koji se javljaju u sobi.
Ovo uključuje praćenje pridruživanja i napuštanja korisnika te primanje poruka od drugih korisnika.

Postoje i drugi slušači događaja koji se pozivaju kada se dogodi greška, kada se veza prekine ili kada primimo poruku u sobi.

Postoje funkcije koje se koriste za stvaranje HTML elemenata za članove sobe i poruke te za ažuriranje DOM-a (HTML-a) kada se dogode 
promjene u članovima ili kada primimo nove poruke.

Postoji i funkcija "sendMessage" koja se poziva kada korisnik pošalje poruku preko forme za unos poruka.
Ova funkcija šalje poruku preko "drone.publish" funkcije i dodaje je u DOM (HTML) kao novu poruku.
