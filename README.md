<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework. You can also check out [Laravel Learn](https://laravel.com/learn), where you will be guided through building a modern Laravel application.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Redberry](https://redberry.international/laravel-development)**
- **[Active Logic](https://activelogic.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
CAHIER DES CHARGES 
TECHNIQUE COMPLET 
Plateforme Intelligente de Gestion des Offres et Demandes d'Emploi 
Messagerie Temps Réel · IA & Matching · Notifications · Administration Complète 
Paramètre 
Valeur 
Version 
3.0 – Édition Complète 
Date 
Mars 2026 
Backend 
PHP 8.x · MVC · API REST + WebSocket 
Frontend 
React 18 · Axios · React Query · TailwindCSS 
Base de données 
Cloudflare D1 (SQLite serverless) 
Stockage 
Cloudflare R2 (CV, logos, avatars, pièces jointes) 
Hébergement 
Cloudflare Workers / Pages 
Temps réel 
WebSocket (Ratchet PHP / Cloudflare Durable Objects) 
IA / Matching 
OpenAI API · score cosinus · modération NLP 
Auth 
JWT HS256 · HttpOnly Cookie · RBAC 4 rôles 
1. Résumé Exécutif et Périmètre 
Cette plateforme vise à connecter efficacement entreprises et candidats grâce à une application web 
moderne, sécurisée et intelligente. Elle intègre un moteur de matching alimenté par IA, une messagerie 
temps réel, un système de notifications multi-canal, et une administration complète avec tableau de bord 
analytique. 
Module 
Fonctionnalités clés 
Authentification & Rôles 
Technologie associée 
Inscription, SSO, 2FA, RBAC 
Offres & Candidatures 
JWT, PHP, bcrypt 
Publication, recherche, suivi 
D1, R2, React 
Messagerie Temps Réel 
Chat, fichiers, statuts de lecture 
IA & Matching 
WebSocket, D1, R2 
Score profil/offre, 
recommandations 
Notifications 
In-app, email, alertes emploi 
OpenAI API, NLP, vecteurs 
Administration 
Push, SMTP, cron D1 
Modération, stats, rapports 
Tableau de bord React 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
2. Messagerie en Temps Réel – Spécifications 
Complètes 
2.1 Vue d'ensemble et architecture 
La messagerie repose sur une architecture hybride : un canal WebSocket permanent gère les messages en 
temps réel, tandis que l'API REST PHP sert de fallback et de persistance. Chaque message est stocké en 
Cloudflare D1 et les fichiers joints en Cloudflare R2. 
 
ℹ  La messagerie est accessible uniquement entre un candidat et un recruteur liés par une candidature 
existante, afin d'éviter les spams et d'assurer la pertinence des échanges. 
 
2.2 Endpoints API – Messagerie 
Méthode Route Description Auth 
GET /messages/conversations Liste toutes les 
conversations de 
l'utilisateur connecté 
(aperçu dernier message, 
nb non lus) 
JWT requis 
GET /messages/conversations/{conv_id} Détail d'une conversation 
avec historique paginé 
(50 messages par page, 
cursor-based) 
JWT requis 
POST /messages Envoyer un nouveau 
message texte ou avec 
pièce jointe 
JWT requis 
PATCH /messages/{id}/read Marquer un message 
spécifique comme lu 
JWT requis 
PATCH /messages/conversations/{conv_id}/read
all Tout marquer comme lu 
dans une conversation 
JWT requis 
DELETE /messages/{id} Supprimer un message 
(soft delete – visible 
'Message supprimé') 
JWT requis 
POST /messages/attachments Upload d'une pièce jointe 
vers Cloudflare R2 (PDF, 
image max 10Mo) 
JWT requis 
GET /messages/unread-count Nombre total de 
messages non lus (pour 
badge navbar) 
JWT requis 
POST /messages/{id}/report Signaler un message 
comme abusif ou 
inapproprié 
JWT requis 
WS /ws/messages Canal WebSocket temps 
réel – écoute et émission 
de messages 
JWT requis 
 
2.3 Table : messages 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 généré côté PHP 
conv_id TEXT NOT NULL Identifiant de la conversation (hash des 2 
user_id triés) 
expediteur_id TEXT FK → users.id 
NOT NULL 
Auteur du message 
destinataire_id TEXT FK → users.id 
NOT NULL 
Destinataire du message 
application_id TEXT FK → 
applications.id 
Candidature liée (obligatoire pour initier la 
conv) 
contenu TEXT NULL Corps du message (texte brut ou HTML 
sanitisé) 
piece_jointe_url TEXT NULL URL R2 de la pièce jointe (si présente) 
piece_jointe_nom TEXT NULL Nom original du fichier joint 
piece_jointe_mime TEXT NULL Type MIME du fichier (application/pdf, 
image/jpeg…) 
type TEXT DEFAULT 
'text' 
text | file | system (messages automatiques 
du système) 
lu INTEGER DEFAULT 0 0 = non lu, 1 = lu par le destinataire 
lu_at DATETIME NULL Horodatage de lecture 
signale INTEGER DEFAULT 0 1 = signalé par un utilisateur (en attente 
modération) 
deleted_at DATETIME NULL Soft delete – le message affiche 'Message 
supprimé' 
created_at DATETIME NOT NULL Date d'envoi (ISO 8601) 
 
Index SQL : 
CREATE INDEX idx_msg_conv ON messages(conv_id); 
CREATE INDEX idx_msg_exp ON messages(expediteur_id); 
CREATE INDEX idx_msg_dest ON messages(destinataire_id); 
CREATE INDEX idx_msg_lu ON messages(lu); 
CREATE INDEX idx_msg_conv_date ON messages(conv_id, created_at DESC); 
 
2.4 Table : conversations 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
Hash déterministe : SHA1(sort([user1_id, 
user2_id]).join(':')) 
user1_id TEXT FK → users.id Participant 1 (ordre croissant des IDs) 
user2_id TEXT FK → users.id Participant 2 
application_id TEXT FK → 
applications.id 
Candidature à l'origine de la conversation 
last_message_id TEXT FK → 
messages.id 
Dernier message (pour aperçu) 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
last_activity_at DATETIME NOT NULL Date du dernier message (tri liste 
conversations) 
user1_archived INTEGER DEFAULT 0 Conversation archivée côté user1 
user2_archived INTEGER DEFAULT 0 Conversation archivée côté user2 
created_at DATETIME NOT NULL Création de la conversation 
 
2.5 Flux WebSocket temps réel 
Étape Événement Détail 
1 Connexion WS Client envoie token JWT dans le header Upgrade 
2 Auth WS PHP vérifie JWT – attribue user_id à la socket 
3 Join room Client rejoint sa room privée : room_{user_id} 
4 Envoi message emit('message:send', {conv_id, contenu, piece_jointe_url}) 
5 Persist + broadcast PHP sauvegarde en D1, émet 'message:received' à la room 
destinataire 
6 Accusé de lecture emit('message:read', {message_id}) → actualise lu=1 en D1 
7 Typing indicator emit('typing:start'|'typing:stop', {conv_id}) – pas persisté en 
base 
8 Disconnect Nettoyage room, maj statut 'en ligne' de l'utilisateur 
 
▸  Payload WS – Envoi d'un message (client → serveur) 
{ 
  "event": "message:send", 
  "payload": { 
    "conv_id": "conv_abc123", 
    "contenu": "Bonjour, votre candidature est retenue.", 
    "piece_jointe_url": null, 
    "type": "text" 
  } 
} 
 
▸  Payload WS – Message reçu (serveur → client) 
{ 
  "event": "message:received", 
  "payload": { 
    "id": "msg_xyz789", 
    "conv_id": "conv_abc123", 
    "expediteur_id": "usr_rec456", 
    "contenu": "Bonjour, votre candidature est retenue.", 
    "type": "text", 
    "lu": false, 
    "created_at": "2026-03-02T14:30:00Z" 
  } 
} 
 
2.6 Règles métier de la messagerie 
• Une conversation ne peut être initiée que si une candidature active existe entre les deux parties 
• Un candidat ne peut contacter qu'un recruteur lié à une de ses candidatures 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
• Les messages sont limités à 5 000 caractères par message 
• Les pièces jointes acceptées : PDF, PNG, JPG, DOCX – taille max 10 Mo 
• Les messages supprimés restent visibles avec la mention « Message supprimé » pour l'historique 
• Un message signalé 3 fois par des utilisateurs différents déclenche une révision admin automatique 
• Indicateur de présence en ligne : statut mis à jour toutes les 30 secondes via heartbeat WS 
• Les conversations inactives depuis 6 mois sont archivées automatiquement (conservées en lecture 
seule) 
 
3. Système de Notifications – Spécifications Complètes 
3.1 Types de notifications 
Type Déclencheur Canal Destinataire 
nouvelle_candidature Candidat postule In-app + Email Recruteur 
statut_change Recruteur modifie 
statut 
In-app + Email Candidat 
nouveau_message Message reçu In-app + Badge WS Destinataire 
alerte_offre Nouvelle offre = 
alerte 
Email (digest) Candidat abonné 
offre_expiree Date expiration 
atteinte 
In-app + Email Recruteur 
profil_incomplet J+3 après 
inscription 
Email Candidat 
entreprise_validee Admin valide 
entreprise 
Email Recruteur 
compte_suspendu Admin suspend 
compte 
Email Utilisateur 
matching_suggestion Score IA ≥ 80% In-app (hebdomadaire) Candidat 
 
3.2 Endpoints API – Notifications 
Méthode Route Description Auth 
GET /notifications Liste des notifications de 
l'utilisateur (paginée, tri par date 
desc) 
JWT requis 
GET /notifications/unread
count Nombre de notifications non lues 
(badge navbar) 
JWT requis 
PATCH /notifications/{id}/read Marquer une notification comme 
lue 
JWT requis 
PATCH /notifications/read-all Tout marquer comme lu en une 
seule requête 
JWT requis 
DELETE /notifications/{id} Supprimer une notification (soft 
delete) 
JWT requis 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
DELETE /notifications/clear-all Supprimer toutes les notifications 
lues 
JWT requis 
GET /notifications/preferences Paramètres de notification de 
l'utilisateur 
JWT requis 
PUT /notifications/preferences Mettre à jour les préférences 
(désactiver email, etc.) 
JWT requis 
GET /alerts Liste des alertes emploi de 
l'utilisateur 
JWT requis 
POST /alerts Créer une nouvelle alerte emploi 
avec critères 
JWT requis 
PUT /alerts/{id} Modifier les critères d'une alerte JWT requis 
DELETE /alerts/{id} Supprimer une alerte JWT requis 
PATCH /alerts/{id}/toggle Activer ou désactiver une alerte JWT requis 
 
3.3 Table : notifications 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
user_id TEXT FK → 
users.id 
Destinataire de la notification 
type TEXT NOT NULL Cf. tableau types ci-dessus 
titre TEXT NOT NULL Titre court (max 80 car.) 
message TEXT NOT NULL Corps de la notification (max 500 car.) 
lien TEXT NULL URL interne de redirection (ex : /jobs/xyz) 
metadata TEXT NULL JSON : données contextuelles (job_id, app_id, 
score_ia…) 
canal TEXT DEFAULT 
'inapp' 
inapp | email | push | ws 
lu INTEGER DEFAULT 
0 
0 = non lu 
lu_at DATETIME NULL Horodatage de lecture 
envoye_email INTEGER DEFAULT 
0 
1 = email de notification envoyé 
deleted_at DATETIME NULL Soft delete 
created_at DATETIME NOT NULL Date de création 
 
3.4 Table : notification_preferences 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
user_id TEXT FK → 
users.id 
Utilisateur concerné 
email_candidatures INTEGER DEFAULT 
1 
Recevoir emails sur nouvelles candidatures 
email_messages INTEGER DEFAULT 
1 
Recevoir emails sur nouveaux messages 
email_alertes INTEGER DEFAULT 
1 
Recevoir emails d'alertes emploi 
email_statuts INTEGER DEFAULT 
1 
Recevoir emails sur changements de statut 
inapp_messages INTEGER DEFAULT 
1 
Notifications in-app pour messages 
inapp_suggestions_ia INTEGER DEFAULT 
1 
Suggestions IA dans l'app 
frequence_alertes TEXT DEFAULT 
'hebdo' 
instantanee | quotidienne | hebdo 
heure_digest TEXT DEFAULT 
'08:00' 
Heure d'envoi du digest quotidien (HH:MM) 
updated_at DATETIME NOT NULL Dernière modification 
 
3.5 Table : job_alerts 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
user_id TEXT FK → 
users.id 
Candidat propriétaire de l'alerte 
nom TEXT NOT NULL Nom de l'alerte (ex : 'Dev PHP Yaoundé') 
mots_cles TEXT NULL JSON array : ["PHP", "développeur"] 
localisation TEXT NULL Filtre géographique 
type_contrat TEXT NULL CDI | CDD | Stage | … 
salaire_min INTEGER NULL Filtre salaire minimum 
teletravail INTEGER NULL 1 = télétravail uniquement 
frequence TEXT DEFAULT 
'hebdo' 
instantanee | quotidienne | hebdo 
derniere_exec DATETIME NULL Dernière exécution du cron de cette alerte 
active INTEGER DEFAULT 
1 
1 = alerte active 
created_at DATETIME NOT NULL Date de création 
 
4. Intelligence Artificielle & Matching 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
4.1 Fonctionnalités IA 
Fonctionnalité Description Implémentation 
Score Matching Score 0-100 profil/offre Vecteurs OpenAI + similarité cosinus 
Recommandations offres Top 10 offres suggérées au 
candidat 
Embeddings profil vs offres actives 
Suggestions profils Top candidats pour une offre Reverse matching recruteur 
Modération contenu Détection spam / contenu abusif OpenAI Moderation API 
Analyse CV Extraction automatique 
compétences 
OpenAI GPT + prompting structuré 
Résumé automatique Résumé de profil candidat GPT-4o-mini (économique) 
 
4.2 Endpoints API – IA & Matching 
Méthode Route Description Auth 
GET /ai/match/candidate/{id} Top 10 offres recommandées 
pour un candidat (score IA) 
JWT requis 
GET /ai/match/job/{id} Top 20 profils candidats 
correspondants à une offre 
JWT requis 
GET /ai/score/{job_id}/{user_id} Score de compatibilité précis 
entre un profil et une offre 
JWT requis 
POST /ai/analyze-cv Extraire compétences et 
expériences d'un CV PDF 
uploadé 
JWT requis 
POST /ai/moderate Vérifier qu'un contenu respecte 
les règles de la plateforme 
Admin 
POST /ai/summarize-profile/{id} Générer un résumé IA du profil 
candidat 
JWT requis 
GET /ai/suggestions/{user_id} Recommandations 
personnalisées (page d'accueil 
candidat) 
JWT requis 
 
4.3 Table : ai_matching_scores 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
job_id TEXT FK → 
jobs.id NOT 
NULL 
Offre concernée 
user_id TEXT FK → 
users.id 
NOT NULL 
Candidat concerné 
score REAL NOT NULL Score de matching 0.00 à 100.00 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
details TEXT NULL JSON : {competences: 85, experience: 70, 
localisation: 90} 
version_model TEXT NOT NULL Version du modèle IA utilisé (ex: gpt-4o-mini
v1) 
computed_at DATETIME NOT NULL Date de calcul du score 
expires_at DATETIME NOT NULL Date d'expiration du score (recalcul si profil 
modifié) 
 
4.4 Algorithme de matching – Détail 
Le score de matching est calculé selon une pondération multi-critères : 
Critère Poids Méthode de calcul 
Compétences techniques 40% Intersection JSON arrays + embeddings 
Expérience professionnelle 25% Années requises vs déclarées 
Localisation / télétravail 15% Correspondance ville + flag télétravail 
Type de contrat 10% Correspondance exacte ou partielle 
Fourchette salariale 10% Chevauchement des plages salariales 
 
5. Authentification, Rôles et Permissions 
5.1 Endpoints API – Auth 
Méthode Route Description Auth 
POST /auth/register Inscription + envoi email de 
vérification 
Public 
POST /auth/login Connexion – retourne JWT (access 
+ refresh token) 
Public 
POST /auth/logout Invalidation du token (blacklist 
Redis ou D1) 
JWT requis 
GET /auth/verify
email/{token} Validation de l'adresse email via 
token 
Public 
POST /auth/forgot-password Envoi d'un email de réinitialisation Public 
POST /auth/reset-password Changement effectif du mot de 
passe 
Public 
POST /auth/refresh Renouvellement du JWT avant 
expiration 
JWT requis 
GET /auth/me Profil complet de l'utilisateur 
connecté 
JWT requis 
POST /auth/change-password Changement de mot de passe 
(connecté) 
JWT requis 
POST /auth/2fa/enable Activer la double authentification 
(TOTP) 
JWT requis 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
POST /auth/2fa/verify Vérifier le code 2FA lors de la 
connexion 
JWT requis 
 
5.2 Matrice des permissions RBAC 
Action Anonyme Candidat Recruteur Admin 
Voir liste offres ✓ ✓ ✓ ✓ 
Postuler à une offre ✗ ✓ ✗ ✓ 
Publier une offre ✗ ✗ ✓ ✓ 
Voir CV candidat ✗ – Si candidature ✓ 
Envoyer un message ✗ Si candidature Si candidature ✓ 
Valider entreprise ✗ ✗ ✗ ✓ 
Voir stats globales ✗ ✗ Ses propres 
offres 
✓ Toutes 
Supprimer tout contenu ✗ ✗ ✗ ✓ 
 
6. Endpoints Complets – Offres, Candidats, Entreprises 
6.1 Candidats 
Méthode Route Description Auth 
GET /candidates Liste paginée de tous les 
candidats (admin 
uniquement) 
Admin 
GET /candidates/{id} Profil public d'un candidat JWT requis 
PUT /candidates/{id} Mise à jour du profil (infos, 
compétences, statut) 
JWT requis 
DELETE /candidates/{id} Suppression du compte 
(soft delete + RGPD) 
JWT requis 
POST /candidates/{id}/cv Upload CV PDF vers 
Cloudflare R2 
JWT requis 
DELETE /candidates/{id}/cv Supprimer le CV existant 
de R2 + D1 
JWT requis 
GET /candidates/{id}/applications Toutes les candidatures 
d'un candidat avec statuts 
JWT requis 
GET /candidates/{id}/profile-completion Taux de complétion du 
profil (0-100%) 
JWT requis 
POST /candidates/{id}/experiences Ajouter une expérience 
professionnelle 
JWT requis 
PUT /candidates/{id}/experiences/{exp_id} Modifier une expérience JWT requis 
DELETE /candidates/{id}/experiences/{exp_id} Supprimer une expérience JWT requis 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
 
6.2 Entreprises 
Méthode Route Description Auth 
POST /companies Créer un profil entreprise JWT requis 
GET /companies Liste paginée des entreprises 
validées 
Public 
GET /companies/{id} Détail + offres actives de 
l'entreprise 
Public 
PUT /companies/{id} Modifier les informations de 
l'entreprise 
JWT requis 
DELETE /companies/{id} Supprimer l'entreprise (soft 
delete) 
Admin 
POST /companies/{id}/logo Upload logo vers Cloudflare R2 JWT requis 
PATCH /companies/{id}/validate Valider ou rejeter l'entreprise 
(admin) 
Admin 
POST /companies/{id}/members Inviter un co-recruteur dans 
l'entreprise 
JWT requis 
DELETE /companies/{id}/members/{uid} Retirer un membre de l'équipe 
recrutement 
JWT requis 
GET /companies/{id}/stats Statistiques de l'entreprise (vues, 
candidatures, taux conversion) 
JWT requis 
 
6.3 Offres d'emploi 
Méthode Route Description Auth 
POST /jobs Créer une nouvelle offre JWT requis 
GET /jobs Liste paginée des offres publiées Public 
GET /jobs/{id} Détail complet d'une offre + 
candidatures (recruteur) 
Public 
PUT /jobs/{id} Modifier une offre JWT requis 
DELETE /jobs/{id} Archiver une offre (soft delete) JWT requis 
PATCH /jobs/{id}/status Changer statut : brouillon → publiée 
→ expirée 
JWT requis 
POST /jobs/{id}/duplicate Dupliquer en brouillon JWT requis 
GET /jobs/search Recherche full-text multi-critères Public 
GET /jobs/company/{cid} Toutes les offres d'une entreprise Public 
GET /jobs/{id}/stats Vues, candidatures, taux de 
conversion par offre 
JWT requis 
POST /jobs/{id}/report Signaler une offre abusive JWT requis 
POST /jobs/{id}/save Sauvegarder une offre dans ses 
favoris 
JWT requis 
DELETE /jobs/{id}/save Retirer des favoris JWT requis 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
GET /jobs/saved Liste des offres sauvegardées JWT requis 
 
6.4 Candidatures 
Méthode Route Description Auth 
POST /applications Soumettre une candidature JWT requis 
GET /applications Liste de toutes les candidatures 
(admin) 
Admin 
GET /applications/{id} Détail d'une candidature JWT requis 
DELETE /applications/{id} Retirer une candidature (avant 
passage en entretien) 
JWT requis 
PATCH /applications/{id}/status Mettre à jour le statut (recruteur) JWT requis 
GET /applications/job/{job_id} Toutes les candidatures pour 
une offre (kanban recruteur) 
JWT requis 
GET /applications/stats/{job_id} Stats par statut pour une offre 
(graphiques) 
JWT requis 
POST /applications/{id}/note Ajouter une note interne 
recruteur 
JWT requis 
GET /applications/export/{job_id} Exporter candidatures en 
CSV/Excel 
JWT requis 
 
7. Tables Base de Données Cloudflare D1 – Complètes 
7.1 Table : users 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
nom TEXT NOT NULL Nom de famille 
prenom TEXT NOT NULL Prénom 
email TEXT UNIQUE 
NOT NULL 
Email (identifiant unique) 
password TEXT NOT NULL Hash bcrypt (cost 12) 
role TEXT NOT NULL candidat | recruteur | admin | moderateur 
avatar_url TEXT NULL URL R2 photo de profil 
statut TEXT DEFAULT 
'actif' 
actif | suspendu | supprime | en_attente 
email_verifie INTEGER DEFAULT 
0 
0 = non vérifié 
verify_token TEXT NULL Token de vérification email 
reset_token TEXT NULL Token reset password 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
reset_expires DATETIME NULL Expiration token reset 
two_fa_secret TEXT NULL Secret TOTP pour 2FA 
two_fa_active INTEGER DEFAULT 
0 
1 = 2FA activé 
derniere_connexion DATETIME NULL Horodatage dernière connexion 
created_at DATETIME NOT NULL Date d'inscription 
updated_at DATETIME NOT NULL Dernière modification 
deleted_at DATETIME NULL Soft delete RGPD 
 
7.2 Table : candidate_profiles 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
user_id TEXT FK → 
users.id 
Référence utilisateur 
titre_professionnel TEXT NULL Intitulé du poste recherché 
bio TEXT NULL Présentation (max 1000 car.) 
localisation TEXT NULL Ville, pays 
competences TEXT NULL JSON array ["PHP","React"] 
langues TEXT NULL JSON array avec niveaux 
cv_url TEXT NULL URL R2 CV PDF 
cv_nom TEXT NULL Nom original du fichier CV 
cv_ia_analyse TEXT NULL JSON résultat analyse IA du CV 
statut_recherche TEXT DEFAULT 
'actif' 
actif | passif | indisponible 
profil_public INTEGER DEFAULT 
1 
1 = visible dans recherche recruteurs 
experiences TEXT NULL JSON array des expériences 
formations TEXT NULL JSON array des formations 
certifications TEXT NULL JSON array des certifications 
salaire_souhaite INTEGER NULL Prétention salariale (XAF) 
date_disponibilite DATE NULL Date de disponibilité 
linkedin_url TEXT NULL URL profil LinkedIn 
portfolio_url TEXT NULL URL portfolio/GitHub 
embedding_vector TEXT NULL JSON vecteur embedding IA (OpenAI) 
created_at DATETIME NOT NULL Date création profil 
updated_at DATETIME NOT NULL Dernière mise à jour 
 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
7.3 Table : companies 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
user_id TEXT FK → 
users.id 
Propriétaire principal 
nom_entreprise TEXT NOT NULL Raison sociale 
description TEXT NULL Présentation détaillée 
secteur TEXT NULL Secteur d'activité 
taille TEXT NULL 1-10 | 11-50 | 51-200 | 200+ 
site_web TEXT NULL URL site officiel 
localisation TEXT NULL Siège social 
logo_url TEXT NULL URL R2 logo 
statut TEXT DEFAULT 
'pending' 
pending | validee | rejetee | suspendue 
motif_rejet TEXT NULL Raison du rejet (visible recruteur) 
nb_employes INTEGER NULL Nombre d'employés 
annee_creation INTEGER NULL Année de fondation 
deleted_at DATETIME NULL Soft delete 
created_at DATETIME NOT NULL Date création 
updated_at DATETIME NOT NULL Dernière modification 
 
7.4 Table : jobs 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
company_id TEXT FK → 
companies.id 
Entreprise qui publie 
titre TEXT NOT NULL Intitulé du poste 
description TEXT NOT NULL Description (HTML sanitisé) 
localisation TEXT NOT NULL Ville, pays 
type_contrat TEXT NOT NULL CDI | CDD | Stage | Alternance | 
Freelance 
salaire_min INTEGER NULL Fourchette basse (XAF) 
salaire_max INTEGER NULL Fourchette haute (XAF) 
salaire_visible INTEGER DEFAULT 1 0 = salaire masqué (affiche 'À discuter') 
teletravail INTEGER DEFAULT 0 0 = présentiel, 1 = télétravail 
competences_requises TEXT NULL JSON array compétences 
experience_requise TEXT NULL junior | confirme | senior 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
niveau_etude TEXT NULL Bac | Bac+2 | Bac+3 | Bac+5 | Doctorat 
avantages TEXT NULL JSON array : ["Mutuelle", "13e mois"] 
statut TEXT DEFAULT 
'brouillon' 
brouillon | publiee | expiree | archivee 
epingle INTEGER DEFAULT 0 1 = mis en avant (offre sponsorisée) 
nb_vues INTEGER DEFAULT 0 Compteur de vues 
nb_candidatures INTEGER DEFAULT 0 Compteur dénormalisé 
embedding_vector TEXT NULL JSON vecteur embedding IA 
ia_moderee INTEGER DEFAULT 0 1 = contenu vérifié par IA 
date_expiration DATETIME NULL Date limite de candidature 
deleted_at DATETIME NULL Soft delete 
created_at DATETIME NOT NULL Date de publication 
updated_at DATETIME NOT NULL Dernière modification 
 
7.5 Table : applications 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
job_id TEXT FK → 
jobs.id NOT 
NULL 
Offre concernée 
candidate_id TEXT FK → 
users.id 
NOT NULL 
Candidat 
statut TEXT DEFAULT 
'envoyee' 
envoyee | vue | entretien | test_technique | 
refusee | acceptee 
cv_url TEXT NOT NULL URL R2 du CV soumis 
lettre_motivation TEXT NULL Lettre de motivation 
note_recruteur REAL NULL Note interne (1-5) 
commentaire_recruteur TEXT NULL Note privée recruteur (non visible 
candidat) 
score_ia REAL NULL Score matching IA calculé à la 
candidature 
date_entretien DATETIME NULL Date convoquée pour l'entretien 
lien_entretien TEXT NULL URL visioconférence (Meet, Teams…) 
vue_at DATETIME NULL Horodatage 1ère ouverture par recruteur 
deleted_at DATETIME NULL Soft delete 
created_at DATETIME NOT NULL Date de candidature 
updated_at DATETIME NOT NULL Dernière modification 
 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
7.6 Table : saved_jobs 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
user_id TEXT FK → 
users.id 
Candidat qui sauvegarde 
job_id TEXT FK → 
jobs.id 
Offre sauvegardée 
created_at DATETIME NOT NULL Date de sauvegarde 
 
7.7 Table : company_members 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
company_id TEXT FK → 
companies.id 
Entreprise 
user_id TEXT FK → 
users.id 
Membre de l'équipe recrutement 
role_equipe TEXT DEFAULT 
'recruteur' 
admin_rh | recruteur 
created_at DATETIME NOT NULL Date d'ajout 
 
7.8 Table : reports (signalements) 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
reporter_id TEXT FK → 
users.id 
Auteur du signalement 
cible_type TEXT NOT NULL job | message | user | company 
cible_id TEXT NOT NULL ID de l'élément signalé 
raison TEXT NOT NULL spam | abusif | faux | discriminatoire | autre 
detail TEXT NULL Description complémentaire 
statut TEXT DEFAULT 
'ouvert' 
ouvert | traite | rejete 
traite_par TEXT NULL FK → users.id (admin/moderateur) 
traite_at DATETIME NULL Date de traitement 
created_at DATETIME NOT NULL Date du signalement 
 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
8. Administration et Modération – Endpoints Complets 
8.1 Tableau de bord admin 
Méthode Route Description Auth 
GET /admin/stats/overview KPIs globaux : users, offres, 
candidatures, messages du jour 
Admin 
GET /admin/stats/growth Courbes de croissance 7j/30j/90j 
(inscriptions, offres) 
Admin 
GET /admin/stats/conversion Taux de conversion candidature → 
entretien → accepté 
Admin 
GET /admin/stats/top
companies Top entreprises par nombre d'offres 
et candidatures 
Admin 
GET /admin/stats/top-jobs Offres les plus vues et les plus 
postulées 
Admin 
GET /admin/stats/export Export CSV ou Excel des 
statistiques sur une période 
Admin 
 
8.2 Gestion utilisateurs 
Méthode Route Description Auth 
GET /admin/users Liste paginée de tous les 
utilisateurs avec filtres 
Admin 
GET /admin/users/{id} Détail complet d'un utilisateur Admin 
PATCH /admin/users/{id}/status Activer / suspendre / supprimer un 
compte 
Admin 
PATCH /admin/users/{id}/role Changer le rôle d'un utilisateur Admin 
DELETE /admin/users/{id} Suppression définitive + 
anonymisation RGPD 
Admin 
GET /admin/users/{id}/activity Journal des actions de l'utilisateur 
(audit log) 
Admin 
 
8.3 Modération 
Méthode Route Description Auth 
GET /admin/reports Liste des signalements en 
attente (triés par gravité) 
Admin 
GET /admin/reports/{id} Détail d'un signalement avec 
contexte 
Admin 
PATCH /admin/reports/{id}/resolve Traiter un signalement (action + 
commentaire) 
Admin 
GET /admin/moderation/messages Messages signalés en attente 
de révision 
Admin 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
GET /admin/moderation/jobs Offres signalées en attente de 
révision 
Admin 
DELETE /admin/moderation/jobs/{id} Supprimer une offre abusive Admin 
POST /admin/moderation/ai-scan Lancer un scan IA sur les 
contenus récents 
Admin 
GET /admin/companies/pending Entreprises en attente de 
validation 
Admin 
PATCH /admin/companies/{id}/validate Valider ou rejeter avec motif Admin 
 
8.4 Table : audit_logs 
Champ Type SQL Contrainte Description 
id TEXT PRIMARY 
KEY 
UUID v4 
user_id TEXT FK → 
users.id 
Utilisateur qui a effectué l'action 
action TEXT NOT NULL login | logout | create_job | delete_user | 
validate_company… 
cible_type TEXT NULL Type de l'entité affectée (user, job, 
company…) 
cible_id TEXT NULL ID de l'entité affectée 
details TEXT NULL JSON : données avant/après modification 
ip_address TEXT NULL Adresse IP de la requête 
user_agent TEXT NULL User-Agent du navigateur 
created_at DATETIME NOT NULL Date et heure de l'action 
 
9. Gestion des Fichiers – Cloudflare R2 
9.1 Organisation des buckets 
Préfixe R2 Contenu Règle de nommage + TTL 
cv/ CV candidats (PDF 
uniquement) 
cv/{user_id}_{ts}.pdf – URL 
signée 1h 
logos/ Logos entreprises 
(PNG/JPG) 
logos/{company_id}.{ext} – URL 
publique 
avatars/ Photos de profil (PNG/JPG) avatars/{user_id}.{ext} – URL 
publique 
attachments/ Pièces jointes messagerie attachments/{msg_id}_{fn} – 
URL signée 24h 
exports/ Exports CSV/Excel admin exports/{admin_id}_{ts}.csv – 
URL signée 15min 
 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
9.2 Règles de validation 
Type fichier 
MIME acceptés 
Taille max 
CV 
Validation supplémentaire 
application/pdf 
5 Mo 
Vérification magic bytes PDF 
(%PDF-) 
Logo 
image/png, 
image/jpeg 
2 Mo 
Resize auto 400x400px côté 
serveur 
Avatar 
image/png, 
image/jpeg 
1 Mo 
Resize auto 200x200px + crop 
carré 
Pièce jointe 
PDF, PNG, JPG, 
DOCX 
10 Mo 
Scan antivirus si disponible 
10. Sécurité – Spécifications Complètes 
10.1 Authentification JWT 
Token 
Durée de vie 
Access Token 
Stockage recommandé 
1 heure 
HttpOnly Cookie (Secure, 
SameSite=Strict) 
Refresh Token 
7 jours 
Token 2FA 
5 minutes 
HttpOnly Cookie – renouvelé à 
chaque usage 
Mémoire client uniquement (non 
persisté) 
Token email 
24 heures 
10.2 Règles de sécurité 
Lien URL uniquement – supprimé 
après usage 
• Hachage des mots de passe : password_hash() avec PASSWORD_BCRYPT, cost 12 
• Toutes les requêtes D1 via requêtes préparées PDO – protection injection SQL 
• Validation et sanitisation de toutes les entrées (filter_var, htmlspecialchars, strip_tags) 
• Rate limiting : 60 req/min (public) / 200 req/min (authentifié) / 10 req/min (auth endpoints) 
• En-têtes HTTP de sécurité : HSTS, X-Content-Type-Options, X-Frame-Options, CSP 
• Protection CORS : origines autorisées explicitement définies (domaine React uniquement) 
• Journalisation dans audit_logs de toutes les actions sensibles 
• Vérification magic bytes sur tous les fichiers uploadés 
• Expiration automatique des sessions inactives après 30 minutes 
• Blocage IP après 5 tentatives de connexion échouées (ban 15 minutes) 
11. Interface Frontend React – Vue Complète 
11.1 Architecture React 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
• React 18 avec hooks (useState, useEffect, useContext, useReducer) 
• Routing : React Router v6 – routes publiques, protégées et avec vérification de rôle 
• Gestion d'état : Context API (auth, notifications) + Zustand (état global léger) 
• Cache API : React Query (TanStack) – invalidation automatique après mutation 
• Formulaires : React Hook Form + validation Zod (schémas typés) 
• HTTP : Axios avec intercepteurs JWT (ajout header + refresh automatique) 
• UI : TailwindCSS + composants shadcn/ui + animations Framer Motion 
• Temps réel : socket.io-client (reconnexion automatique, gestion des événements) 
 
11.2 Composants clés de la messagerie côté React 
Composant Fonctionnalités 
<ConversationList /> Liste conversations triées par activité, badge nb messages non lus, 
prévisualisation dernier msg 
<ChatWindow /> Historique paginé (scroll infini), bulles de messages, statut lu/non lu, 
indicateur de frappe 
<MessageBubble /> Affichage message (texte/fichier), horodatage, icône lu, option 
suppression/signalement 
<MessageInput /> Zone de saisie, bouton pièce jointe, envoi sur Entrée, aperçu fichier 
avant envoi, compteur caractères 
<TypingIndicator /> Animation 3 points quand l'interlocuteur est en train d'écrire 
<OnlineStatus /> Point vert/gris indiquant si l'interlocuteur est en ligne (via WebSocket) 
 
11.3 Pages et routes 
Section Page Route Rôle 
Public Accueil + recherche offres / Tous 
Public Détail offre /jobs/:id Tous 
Public Profil entreprise /companies/:id Tous 
Auth Inscription (choix rôle) /register Anonyme 
Auth Connexion + 2FA /login Anonyme 
Candidat Dashboard + 
recommandations IA 
/dashboard Candidat 
Candidat Mon profil + upload CV /profile Candidat 
Candidat Mes candidatures (kanban) /my-applications Candidat 
Candidat Offres sauvegardées /saved-jobs Candidat 
Candidat Mes alertes emploi /alerts Candidat 
Recruteur Dashboard recruteur /recruiter Recruteur 
Recruteur Publier / modifier offre /recruiter/jobs/new Recruteur 
Recruteur Candidatures par offre /recruiter/jobs/:id/apps Recruteur 
Recruteur Stats entreprise /recruiter/stats Recruteur 
CDC Technique Complet v3  |  Plateforme Emploi Intelligente  |  PHP · React · Cloudflare D1/R2 · IA 
FABRICE -TABITA - GRACE – Version 1.0 – Mars 2026 
Commun Messagerie (conversations) /messages JWT requis 
Commun Notifications /notifications JWT requis 
Admin Tableau de bord /admin Admin 
Admin Gestion utilisateurs /admin/users Admin 
Admin Modération + signalements /admin/moderation Admin 
Admin Entreprises en attente /admin/companies Admin 
Admin Statistiques avancées /admin/stats Admin 
 
12. Exigences Non Fonctionnelles 
Domaine Exigence 
Performance API < 200ms (p95) – Page load < 2s sur 4G – LCP < 2,5s 
WebSocket Latence message < 100ms – Reconnexion automatique < 3s – Support 500 
connexions simultanées 
Responsive Mobile first – breakpoints 375/768/1280px – testé iOS Safari & Chrome Android 
SEO Meta dynamiques, sitemap XML, URLs lisibles, données structurées 
Schema.org JobPosting 
Accessibilité WCAG 2.1 niveau AA – navigation clavier – labels ARIA – score Lighthouse ≥ 
90 
Disponibilité SLA 99,5% mensuel – RTO < 2h – RPO < 24h 
Sécurité OWASP Top 10 – audit trimestriel – tests de pénétration avant mise en prod 
RGPD Consentement explicite – export données – droit d'effacement – hébergement 
EU 
Maintenabilité PSR-12 PHP – ESLint/Prettier JS – couverture tests > 70% – Swagger à jour 
Scalabilité Architecture stateless – Cloudflare Workers scalent automatiquement à la