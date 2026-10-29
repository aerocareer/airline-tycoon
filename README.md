# ✈️ AeroCareer Airline Tycoon

**AeroCareer Airline Tycoon** est une plateforme web interactive et coopérative de gestion de compagnie aérienne (Airline Tycoon), conçue spécialement pour accompagner, enrichir et donner un objectif économique concret à vos sessions de simulation de vol réalistes (**Microsoft Flight Simulator 2024 / 2020**, **X-Plane 12**, **DCS World**, **IL-2 Sturmovik**, etc.).

Développé avec des technologies web modernes (HTML5, JavaScript ES6+, Tailwind CSS) et entièrement synchronisé en temps réel via **Google Firebase Firestore**, AeroCareer vous permet de créer un véritable salon coopératif virtuel avec vos amis. Vous gérez ensemble la croissance d'une flotte, la rentabilité financière, les stocks de carburant et la conquête d'un réseau mondial de 100 hubs internationaux.

---

## 🌟 Sommaire

1. [Concept & Philosophie du Jeu](#-concept--philosophie-du-jeu)
2. [Fonctionnalités Détaillées](#-fonctionnalités-détaillées)
   * [1. Multijoueur Cloud & Synchronisation Temps Réel](#1-multijoueur-cloud--synchronisation-temps-réel)
   * [2. Organigramme & Rôles Exécutifs Spécialisés](#2-organigramme--rôles-exécutifs-spécialisés)
   * [3. Marché Énergétique & Logistique du Kérosène (en Kg)](#3-marché-énergétique--logistique-du-kérosène-en-kg)
   * [4. Gestion Financement, Flotte & Leasing](#4-gestion-financement-flotte--leasing)
   * [5. Réseau Mondial des 100 Hubs & Contrats Géolocalisés](#5-réseau-mondial-des-100-hubs--contrats-géolocalisés)
   * [6. Passeport, Trophées & Leaderboard des Pilotes](#6-passeport-trophées--leaderboard-des-pilotes)
3. [Spécifications Techniques & Performance](#-spécifications-techniques--performance)
4. [Feuille de Route & Idées de Développement (Roadmap)](#-feuille-de-route--idées-de-développement-roadmap)
5. [Contact, Support & Communauté](#-contact-support--communauté)

---

## 🎯 Concept & Philosophie du Jeu

Dans la plupart des simulateurs de vol modernes, le pilote enchaîne les vols sans véritable impact à long terme sur un environnement partagé. **AeroCareer** vient combler ce manque en apportant une couche managériale et logistique poussée :

* **Chaque litre de kérosène compte :** Vous devez acheter le carburant au meilleur prix du marché, le stocker dans vos propres cuves et veiller à la consommation réelle de vos appareils.
* **Chaque vol a une valeur financière :** Réalisez des vols de ligne réguliers (PAX) ou du fret lourd (Cargo) pour injecter des liquidités dans la trésorerie commune de l'entreprise.
* **Une expérience coopérative :** Ne volez plus seul. Répartissez-vous les rôles de direction (CEO, CFO, CLO) et collaborez avec votre corps de pilotes pour faire monter la réputation de votre compagnie jusqu'à 100 %.

---

## 🚀 Fonctionnalités Détaillées

### 1. 🌐 Multijoueur Cloud & Synchronisation Temps Réel
* **Salons Cloud partagés :** Créez votre entreprise avec un code unique généré automatiquement (ex: `BEAZ-20261029-X8F`) ou rejoignez instantanément une compagnie existante.
* **Moteur d'Événements Live (Firestore) :** Chaque action (achat d'avion, souscription d'un emprunt, atterrissage d'un vol, ravitaillement des cuves) est propagée en temps réel auprès de tous les joueurs connectés au salon sans besoin de rafraîchir la page.
* **Sauvegarde Automatique de Session :** Le navigateur enregistre vos clés d'accès locales pour vous réauthentifier en un seul clic à vos compagnies lors de vos prochaines visites.

---

### 2. 👥 Organigramme & Rôles Exécutifs Spécialisés (WIP)

Chaque membre de l'équipe peut se voir attribuer un rôle clé dans l'organisation, assorti de privilèges et de responsabilités dédiées :

* **👑 PDG / CEO (Chief Executive Officer) :**
  * Supervise la vision stratégique globale et l'image de marque de la compagnie.
  * Valide l'acquisition et l'ouverture de nouveaux hubs parmi les 100 plateformes mondiales.
  * Gère l'effectif, réattribue les rôles des employés, procède aux recrutements ou aux licenciements.
* **💼 Trésorier / CFO (Chief Financial Officer) :**
  * Pilote la santé financière et analyse le bilan comptable par cycle de 24h (Tick).
  * Gère l'acquisition de la flotte : achats d'appareils neufs ou contrats de leasing courte/longue durée.
  * Négocie et souscrit les emprunts bancaires (court, moyen et long terme) pour financer les investissements lourds.
* **📦 Logisticien / CLO (Chief Logistics Officer) :**
  * Gère la chaîne d'approvisionnement en carburant sur l'ensemble du réseau d'escales.
  * Analyse les fluctuations horaires du cours du pétrole et passe les commandes de ravitaillement direct.
  * Anticipe la volatilité du marché en activant des contrats de couverture boursière (*Fuel Hedging*).
* **👩‍✈️ Pilote de Ligne :**
  * Sélectionne et prend en charge les contrats de vol disponibles au départ de sa position actuelle.
  * Réalise la préparation de vol (calcul du devis carburant en Kg et embarquement à bord).
  * Remplit le formulaire de débriefing à l'arrivée (heures de vol, carburant consommé) et fait progresser ses statistiques personnelles.

---

### 3. 🛢️ Marché Énergétique & Logistique du Kérosène (en Kg)

La gestion du carburant est l'un des piliers économiques centraux d'AeroCareer :

* **Masse en Kilogrammes (Kg) :** Conformément aux standards réels de l'aviation commerciale, toutes les réserves, capacités de cuves et consommations en vol sont calculées précisément en **Kg**.
* **Cours Spot Fluctuant :** Le prix du kérosène au kilo évolue dynamiquement toutes les heures. Un graphique de cours interactif (*Chart.js*) permet au CLO de visualiser les tendances historiques et de repérer les meilleurs moments pour acheter.
* **Contrat de Couverture (*Fuel Hedging*) :** Pour se protéger contre les flambées des prix du pétrole, la compagnie peut verser un acompte pour bloquer le prix du Kg de kérosène au tarif spot actuel pendant une période ferme de **12 ticks (12 cycles de 24h)**.
* **Capacité des Cuves par Hub :** Chaque hub réseau possède une cuve dédiée avec une capacité maximale de stockage (ex: 80 000 Kg à Chambéry LFLB, 50 000 Kg à Bourges LFLD, 200 000 Kg à Paris CDG). 
* **Initialisation à 50% & Taxe FBO :** À la création d'une compagnie ou lors de l'achat d'un nouveau hub, les cuves sont automatiquement pré-remplies à **50 % de leur capacité maximale**. Si un pilote effectue un plein dans un aéroport tiers non possédé par la compagnie, une surtaxe FBO de **+25 %** est appliquée sur le prix du carburant.

---

### 4. 📈 Gestion Financement, Flotte & Leasing

* **Catalogue d'Avions Diversifié :** Un vaste choix d'aéronefs couvrant toutes les catégories du simulateur :
  * *Aviation Légère :* Cessna 172 Skyhawk, Diamond DA62.
  * *Turbopropulseurs :* Cessna 208B Grand Caravan, Daher TBM 930, Beechcraft King Air 350i.
  * *Lignes Régionales :* ATR 42-600, ATR 72-600.
  * *Moyens-Porteurs :* Airbus A320neo, Boeing 737-800, Boeing 737 MAX 8.
  * *Longs-Courriers & Fret :* Airbus A350-900, Boeing 787-10 Dreamliner, Airbus A380-800, Boeing 777F.
* **Achat Cash vs Leasing :** Payez l'intégralité de l'appareil à la commande ou optez pour une formule de leasing avec des mensualités prélevées à chaque cycle de 24h.
* **Argus & Usure :** Les appareils subissent une décote progressive en fonction de leur nombre d'heures de vol accumulées. La valeur de revente de la flotte est mise à jour en temps réel dans l'actif du bilan comptable.
* **Emprunts Bancaires :** Possibilité de contracter des crédits de 500 000 €, 2 000 000 € ou 10 000 000 € sur 5, 10 ou 20 ticks avec remboursement automatique des traites à minuit.

---

### 5. 🌍 Réseau Mondial des 100 Hubs & Contrats Géolocalisés

* **Base de Données de 100 Hubs :** Une sélection d'aéroports répartis sur tous les continents (Europe, Amérique du Nord, Amérique du Sud, Asie, Moyen-Orient, Océanie, Afrique), classés selon leur prix d'acquisition, leur capacité fret et la taille de leurs cuves de stockage.
* **Système de Contrats Dynamiques :**
  * Les contrats de vol sont générés de manière réaliste en fonction de l'emplacement géographique des pilotes et des hubs de l'entreprise.
  * Prise en compte du nombre de passagers (PAX), du tonnage de fret, de la distance en kilomètres et de l'autonomie maximale de l'appareil sélectionné.
  * **Vols avec Escales :** Certains contrats long-courriers intègrent une étape intermédiaire obligatoire (escale de ravitaillement/changement d'équipage) avant d'atteindre la destination finale.
* **Filtres de Proximité :** Basculez en un clic entre l'affichage des contrats au départ de votre aéroport actuel ou la liste globale des offres disponibles sur l'ensemble du réseau.

---

### 6. 🎖️ Passeport, Trophées & Leaderboard des Pilotes

* **Passeport & Traçabilité des Hubs :** Un passeport virtuel interactif comptabilise et met en valeur chaque aéroport unique dans lequel vous avez atterri au cours de votre carrière (objectif : explorer les 100 hubs du jeu !).
* **Trophées & Succès de Carrière :** Débloquez 15 succès uniques récompensant vos accomplissements :
  * *Heures de vol :* Cadet du Ciel (10h), Commandant de Bord (50h), As Légendaire (500h)...
  * *Finances & Fret :* Premier Million, Magnat des Airs, Gouffre à Kérosène (50 000 Kg consommés)...
  * *Exploration & Précision :* Seigneur des Aéroports, Pilote de Précision (25 vols sans annulation), Globe-Trotter Intercontinental...
* **Classement Général Triable :** Un tableau de bord comparatif de tous les employés et pilotes de l'entreprise, classable à la volée selon :
  1. Le total d'heures de vol cumulées.
  2. Les gains financiers apportés à la compagnie.
  3. L'efficacité économique (Ratio Gain / Heure de vol).
  4. Le volume total de carburant consommé.

---

## 💻 Spécifications Techniques & Performance

* **Interface Utilisateur :** Design sombre (*Dark Mode*) ergonomique, responsive et optimisé pour le second écran d'un setup de simulation (tablettes, ordinateurs portables, écrans secondaires).
* **Aucun Framework Lourd :** Fonctionne en JavaScript natif léger avec Tailwind CSS (UI) et Chart.js (graphiques).
* **Architecture Cloud :** Google Firebase Firestore v10 SDK en mode temps réel (WebSockets).

---

## 🗺️ Feuille de Route & Idées de Développement (Roadmap)

Les évolutions futures à l'étude pour pousser encore plus loin l'immersion :

- [ ] **Météo Dynamique & Surcharges :** Ajustement des consommations de carburant en fonction des vents de face / de travers réels.
- [ ] **Gestion des Incidents & Maintenance :** Planification de visites de révision (C-Check/D-Check) obligatoires selon l'usure des moteurs et systèmes hydrauliques.
- [ ] **Catering & Satisfaction Passagers :** Possibilité de personnaliser les prestations à bord pour faire varier la réputation nette de la compagnie.
- [ ] **Module Vocal & Annonces Passagers :** Intégration d'un panneau d'annonces audio cabine interactif en fonction des phases de vol.

---

## 💬 Contact, Support & Communauté

Le projet **AeroCareer** est développé par un passionné d'aéronautique et de simulation de vol. Les retours d'expérience, rapports de dysfonctionnement et idées de nouvelles fonctionnalités sont essentiels pour faire évoluer la plateforme !

* **Vous observez un bug ou un comportement anormal dans votre salon ?**
* **Vous souhaitez proposer une idée de mécanique économique ou d'intégration ?**

📧 **Contactez-moi directement par e-mail :**  
👉 **[aerocareer@proton.me](mailto:aerocareer@proton.me)**

*Bon vol à tous les commandants de bord et bonne gestion !* ✈️
