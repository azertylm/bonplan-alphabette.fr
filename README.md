# Bon Plan — La boîte à outils communautaire

> Découvrez, votez et partagez les meilleures trouvailles du quotidien, recommandées par la communauté. Sans pub, sans compte obligatoire, sans backend.

[![Déploiement](https://img.shields.io/badge/déploiement-GitHub%20Pages-FF5C2B?logo=github)]()

🌐 **Version en ligne : [https://azertylm.github.io/bonplan-alphabette.fr/](https://azertylm.github.io/bonplan-alphabette.fr/)**

---

## ✨ Fonctionnalités

| | |
|---|---|
| 🗂️ **40 catégories** | Alimentation, Finance, High-Tech, Maison, Voyage… extensibles (créez les votres, emoji + couleur) |
| 🗳️ **Votes style Reddit** | ▲▼ par profil pseudo, tri *Top / Tendances / Récents*, couronne 👑 du #1, badge 🔥 en feu |
| 🔎 **Recherche globale** | Titres, résumés et liens de tous les conseils + filtres par domaine (💻 Tech, 💰 Finance, 🏠 Maison, 🧺 Vie pratique, 🎉 Loisirs) |
| 👤 **Comptes ultra-simples** | Connexion par pseudo (sans mot de passe), favoris ★ et votes enregistrés par profil, onglet **Mon Profil** |
| ✨ **IA Gemini** | Bouton *Résumer avec l'IA* dans le formulaire de proposition : titre + résumé auto à partir de l'URL (clé utilisateur, stockée localement) |
| 📱 **PWA hors-ligne** | Installable (mode standalone), Service Worker avec cache des données initiales et polices, pastille de statut réseau |
| ⚙️ **Réglages & Données** | Export / Import JSON de tout votre contenu, clé API, réinitialisation |
| 🤝 **Modération** | Signalement 🚩, masquage automatique à 5 signalements, mode Modo |

## 🚀 Lancer le projet en local

Le site est **100 % statique** : aucun build, aucune installation.

```bash
# Option 1 — le plus simple : ouvrir le fichier
# Double-cliquez sur index.html (l'IA et la PWA resteront actives une fois en ligne)

# Option 2 — serveur local recommandé (pour la PWA et le Service Worker)
npx serve .          # ou
python -m http.server 8000
# puis ouvrez http://localhost:8000
```

> 💡 Le Service Worker ne s'active qu'en `http`/`https` (jamais en `file://`) — c'est voulu.

## ☁️ Déploiement

Le déploiement vers **GitHub Pages** est entièrement automatisé :

1. Le workflow [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) se déclenche à chaque `git push` sur `main` (et manuellement via *Actions → Run workflow*).
2. Dans **Settings → Pages → Source**, sélectionnez **GitHub Actions** (à faire une seule fois).
3. Le site est publié à l'adresse : `https://azertylm.github.io/bonplan-alphabette.fr/`

L'application étant conçue en chemins **relatifs racine** (`./bonplan_manifest.json`, `./bonplan_sw.js`…), elle fonctionne aussi bien à la racine d'un domaine que dans un sous-dossier Pages.

## 📁 Structure du projet

```
.
├── index.html                  # Application complète (HTML/CSS/JS + données initiales)
├── bonplan_manifest.json       # Manifest PWA (mode standalone, thème #0A0A0B / #FF5C2B)
├── bonplan_sw.js               # Service Worker : cache hors-ligne de secours
├── bonplan_icon.svg            # Icône application
├── bonplan_icon_maskable.svg   # Icône adaptée Android (maskable)
└── .github/workflows/deploy.yml # Déploiement automatique GitHub Pages
```

## 🔧 Configuration

- **IA Gemini** : ⚙️ *Réglages & Données* → collez votre clé API ([Google AI Studio](https://aistudio.google.com/)) — elle reste sur votre appareil, aucune donnée ne transite ailleurs.
- **Sauvegarde** : ⚙️ → *Exporter mes données (JSON)* pour migrer vers un autre appareil, *Importer* pour fusionner.

## 📄 Licence

Voir [`LICENSE`](./LICENSE).
