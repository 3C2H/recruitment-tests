Exercice Front-end : La bibliothèque d'Henri Potier
L’énoncé
Il était une fois, une collection de cinq livres racontant les histoires d’un formidable héro nommé Henri Potier.
Tous les enfants du monde trouvaient les histoires de cet adolescent fantastiques.
L’éditeur de cette collection, dans un immense élan de générosité (mais aussi pour booster ses ventes wink),
décida de mettre en place des offres commerciales aussi aléatoires que l’issue des sorts de Ron Weasley.

L’éditeur vous demande de développer un site web de e-commerce comprenant deux interfaces :

La première permet d’afficher les livres que l’on souhaite acheter et d’effectuer une recherche libre
La seconde récapitule le panier où sera appliquée la meilleure offre commerciale possible.
Sachez que l’éditeur attachera une attention toute particulière à la qualité de votre programmation.  

Les ressources
La liste des livres Henri Potier est accessible à l’adresse http://henri-potier.xebia.fr/books en GET.

Les offres commerciales associées sont disponibles (depuis n’importe quel domaine) en GET à l’adresse suivante: http://henri-potier.xebia.fr/books/{ISBN1, ISBN2, ...}/commercialOffers  

Un exemple
Calcule
Pour deux livres (à 35 et 30€), la requête ressemblera à : http://henri-potier.xebia.fr/books/c8fabf68-8374-48fe-a7ea-a00ccd07afff,a460afed-e5e7-4e39-a39d-c885c05db861/commercialOffers

Le service enverra les offres applicables à ce panier sous le format JSON suivant :

{
  "offers": [
    { "type": "percentage", "value": 5 },
    { "type": "minus", "value": 15 },
    { "type": "slice", "sliceValue": 100, "value": 12 }
  ]
}
Le prix attendu pour ce panier devra être 50€.

Quelques explications
La première offre identifiée par un type ‘percentage’ est une réduction s’appliquant sur le prix de l’ensemble des livres. Le montant de la réduction est dans ‘value’;

La deuxième offre identifiée par un type ‘minus’ est une déduction directement applicable en caisse d’un montant de ‘value’;

La troisième offre identifiée par un type ‘slice’ est un remboursement par tranche d’achat. Dans cet exemple, on rembourse 12€ par tranche de 100€ d’achat.

Au-delà de « l’exercice imposé », toute idée originale supplémentaire sera appréciée.
