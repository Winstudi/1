# À Table — Prototype V1

Un jeu 3D à la première personne : acheter, aménager et tenir son premier restaurant.

## Lancer

Sur ordinateur : décompresser tout le ZIP, puis ouvrir `index.html` avec un navigateur disposant de WebGL. Tous les fichiers nécessaires sont inclus ; aucun compte ni clé API.

Sur iPhone : les fichiers doivent être servis par un hébergement web statique, puis ouverts dans Safari. L’aperçu de l’app Fichiers ne constitue pas un navigateur de jeu. Cette livraison contient les sources web, pas une application iOS signée ni un site déjà publié.

Pour un essai sur réseau local depuis un ordinateur avec Python : lancer `python3 -m http.server 8080` dans le dossier, puis ouvrir `http://ADRESSE-IP-DE-L-ORDINATEUR:8080` sur l’iPhone connecté au même Wi-Fi.

## Commandes

- Mobile : joystick gauche pour avancer/reculer et se déplacer latéralement. Glisser sur la scène à droite pour regarder. Viser un objet avec le point central et toucher l’action.
- Ordinateur : ZQSD, WASD ou flèches ; glisser la souris pour la vue ; E pour interagir.
- Aménagement : choisir un meuble, regarder vers le sol, déplacer la vue et/ou le joueur, rotation à 90°, puis valider. R fait aussi pivoter.
- Déplacement d’un meuble : Aménager → Déplacer des meubles, puis viser le meuble. Revente au prix d’achat possible depuis le placement.
- Pause : suspend le temps. Le passage en arrière-plan met en pause.

## Première journée

Budget initial : 900 €. Achat du local : 250 €. Équipement minimum : 430 € au total (1 table, 2 chaises, 1 caisse, 1 réfrigérateur, 1 plan de travail et 1 plaque). Solde : 220 €.

Placer les chaises à proximité de la table, à moins de 1,7 m du centre, avec un espace libre pour y accéder. La chaise regarde à l’opposé de son dossier. Le passage de la porte reste réservé.

Ouvrir sur la pancarte devant le local. Les premiers clients entrent et s’installent. Prendre leur commande en les visant.

Une recette : burger maison.
1. Réfrigérateur : prendre une portion d’ingrédients.
2. Plan de travail : préparer (2 secondes).
3. Plaque : lancer la cuisson (5 secondes), puis récupérer.
4. Plan de travail : dresser (1,5 seconde).
5. Client : servir.
6. Après son repas : encaisser à la caisse, puis le client repart.

Vente : 18 € plus un pourboire de 1 à 6 € selon la patience restante au service. Six portions initiales offertes. Quand le réfrigérateur est vide, acheter six portions pour 18 €.

Une journée dure quatre minutes de jeu. Fermer manuellement arrête aussi les arrivées. Les clients déjà présents terminent leur service avant le bilan et le jour suivant. Un client impatient repart sans payer. Le paiement à la caisse reste disponible sans limite de patience une fois le repas servi.

## Sauvegarde

Automatique après les actions importantes, toutes les quatre secondes de jeu et à la mise en arrière-plan. Argent, jours, meubles, ingrédients, cuisson, commandes, clients et position sont conservés dans le stockage local du navigateur. Reprise en pause. Aucune progression hors ligne.

Les sauvegardes restent liées au navigateur et à l’adresse web. Effacer les données du navigateur ou changer d’adresse ne les transfère pas. En navigation privée ou si le stockage est refusé, la persistance peut être indisponible et un message l’indique. Une préparation interrompue avant sa fin reprend à son étape précédente, sans perte de l’ingrédient.

## Périmètre

Modèles 3D stylisés construits en code, commandes tactiles et souris/clavier. Navigation des clients sur une grille évitant le mobilier ; collisions du joueur ; placement à pas de 10 cm et rotation de 90°. Une seule cuisson simultanée dans cette V1, même avec plusieurs plaques. Les clients partagent une table si plusieurs chaises sont disponibles.

Pas encore de recrutement, d’agrandissement, de nouvelles recettes, de compte en ligne, de multijoueur ou de publication App Store. La fluidité et le confort doivent être validés sur un iPhone physique.

## Fichiers

- index.html : interface.
- style.css : mise en page tactile et responsive.
- game.js : scène 3D, règles, navigation et sauvegarde.
- three.min.js : moteur Three.js r160 inclus localement.
- THREE-LICENSE.txt : licence MIT de Three.js.

## Vérification effectuée

Tests automatisés dans Chromium, viewport mobile 390 × 844 : achat du local depuis le bouton visé, mouvement au joystick, achat/rotation/placement d’une table, revente et remboursement, refus d’un placement devant la porte, navigation d’un client, commande, préparation, cuisson chronométrée, dressage, service, repas, paiement, départ, passage au jour 2 et rechargement de la sauvegarde. Départ d’un client impatient également vérifié. Aucune erreur JavaScript lors du parcours de service testé. Ce contrôle ne remplace pas un test sur Safari/iPhone physique.
