# Brief — Application de prise de contacts · Salon des Maires 2026 (v1)

## Objectif
Remplacer la fiche papier « Fiche de prise de contacts » par une application Android
utilisable par 3 commerciaux Biogents France sur le stand, du 24 au 26 novembre 2026.
Chaque contact saisi arrive dans HubSpot avec une tâche de relance, et dans un CSV.
Réutilisable pour les salons suivants.

## Format technique
- Web-app installable sur Android (PWA) : un lien, « Ajouter à l'écran d'accueil ». Pas de Play Store.
- Fonctionne SANS réseau : contacts stockés sur le téléphone, envoyés dès que le réseau revient.
- Paramètre « Salon » (nom + dates) modifiable pour réutiliser l'application.
- Au premier lancement, le commercial choisit son nom (3 noms) et le garde.

## Fiche contact (reprise exacte de la fiche papier v2)
| Bloc | Champs | Type de saisie |
|---|---|---|
| Contact | Nom / Prénom · Fonction (texte) | texte |
| | Maire · Élu · DGS · Tech. | 1 bouton |
| Collectivité | Commune / Interco · Dépt · Nb hab. | texte / numérique |
| Coordonnées | Tél. · E-mail | clavier tél. / email |
| | Accepte d'être recontacté (RGPD) | case, obligatoire pour la relance email |
| Besoin | Remarques | texte libre |
| Quel piège ? | Urban trap · BG-GAT · Hydrofilm (plusieurs possibles) · Qté | boutons + numérique |
| Suite à donner | Devis · RDV · Doc · Rappel (plusieurs possibles) | boutons |
| | Urgence 1 / 2 / 3 | 1 bouton |
| Auto | Commercial · Salon · Date/heure | automatique |

Urgence : 1 = rappel sous 48 h · 2 = sous 15 jours · 3 = information / veille.

## Envoi vers HubSpot (pour chaque contact)
1. Contact (dédoublonné par email) + Entreprise = la commune.
2. Transaction dans « Pipeline leads », étape « A contacter »,
   nom : « Salon des Maires 2026 – {Commune} – {Pièges} ».
3. Tâche de relance assignée à [À CONFIRMER], échéance selon l'urgence :
   1 → J+2 (priorité haute) · 2 → J+15 · 3 → J+30 (priorité basse).
4. Note avec besoin, pièges, quantité et suites à donner.

## Email de remerciement
- Envoyé seulement si la case RGPD est cochée.
- Expéditeur, moment d'envoi et brochure : [À CONFIRMER].

## Export CSV
- Bouton « Exporter » dans l'application : un CSV par jour et par commercial, ou tout le salon.
- Colonnes = champs de la fiche, séparateur « ; », encodage UTF-8 (ouverture directe dans Excel).

## Écrans
1. Liste des contacts du jour (compteur, statut « envoyé / en attente »).
2. Gros bouton « + Nouveau contact ».
3. Formulaire sur un seul écran, saisie en moins de 45 s.
4. Export CSV.

## Hors périmètre v1
Scan de cartes de visite. Scan du QR code des badges : [À CONFIRMER selon le contenu du QR].
