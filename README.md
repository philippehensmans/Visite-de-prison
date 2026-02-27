# Suivi Visites Détenus

Application web progressive (PWA) de suivi des visites en prison. Permet aux visiteurs, aumôniers ou travailleurs sociaux de gérer les fiches de détenus, enregistrer les visites et suivre les actions en cours.

## Fonctionnalités

### Gestion des détenus
- Création, modification et suppression de fiches (nom, cellule)
- Marquage "visité" / "non visité" par simple clic
- Archivage des fiches inactives
- Sélection multiple et suppression groupée

### Visites
- Enregistrement des visites avec date et notes
- Historique complet par détenu (ordre antéchronologique)
- Modification et suppression de visites individuelles

### Suivis
- Ajout de suivis (actions à faire) par détenu
- Vue globale de tous les suivis avec filtres (à faire / fait / tout)
- Marquage comme terminé avec date de complétion
- Badge de compteur sur l'onglet Suivis

### Recherche et tri
- Recherche en temps réel (nom, cellule, notes)
- Tri par nom, cellule ou date de dernière visite
- Filtre par statut de visite (tous / visités / non visités)

### Import / Export
- Import de fichiers Excel (`.xlsx`, `.xls`) avec détection automatique des colonnes
- Export de toutes les fiches actives vers Excel

### Hors-ligne et mobile
- Fonctionne sans connexion internet (Service Worker)
- Installable sur l'écran d'accueil (iOS / Android)
- Interface optimisée pour mobile

## Structure du projet

```
Visite-de-prison/
├── index.html       # Application complète (HTML + CSS + JS)
├── manifest.json    # Manifeste PWA
├── sw.js            # Service Worker (cache hors-ligne)
├── xlsx.min.js      # Bibliothèque Excel (SheetJS)
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## Stack technique

- **Vanilla JavaScript** — aucun framework, moteur de rendu DOM custom (`h()`)
- **localStorage** — persistance des données côté navigateur
- **Service Worker** — cache hors-ligne, stratégie stale-while-revalidate
- **SheetJS (XLSX)** — import/export Excel
- **Google Fonts** — Source Serif 4

## Utilisation

Ouvrir `index.html` dans un navigateur. Aucune installation ni serveur requis.

Pour l'installer comme application sur mobile :
1. Ouvrir dans Safari (iOS) ou Chrome (Android)
2. **iOS** : Partager → "Sur l'écran d'accueil"
3. **Android** : Menu → "Installer l'application"

## Données

Toutes les données sont stockées localement dans le navigateur (`localStorage`). Aucune donnée n'est envoyée à un serveur. Pensez à exporter régulièrement vos données via la fonction Export Excel.
