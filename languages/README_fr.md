# FontFixer

[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | Français

Une extension légère qui optimise les polices des pages web pour une lecture confortable. Changez la famille de police, la taille et les couleurs du texte en un clic.

> Chromium · Manifest V3 · Permissions minimales · Aucun suivi

---

## Pourquoi FontFixer ?

De nombreux sites web utilisent des petites polices, floues ou difficiles à lire. FontFixer vous permet d'ajuster les polices des pages web avec votre typographie préférée, de modifier la taille de police et de personnaliser les couleurs du texte et des liens — le tout en temps réel, sans rechargement de page.

| Avantage | Détail |
|-----------|--------|
| 🔤 **Support des polices locales** | Lit les polices installées sur votre appareil via l'API `queryLocalFonts` |
| ⚡ **Prévisualisation en temps réel** | Toutes les modifications s'appliquent instantanément pendant que vous ajustez — aucun rechargement |
| 💾 **Mémoire par site** | Sauvegarde des réglages de police différents pour différents sites web |
| ⚙️ **Application automatique** | Réapplique les réglages sauvegardés automatiquement à chaque visite sur un site configuré |
| 🔒 **Permissions** | `storage` + `scripting` + `activeTab` ; accès `<all_urls>` uniquement pour injecter les polices sur les sites que vous configurez |

---

## Fonctionnalités

### 🆓 Gratuit

| Fonctionnalité | Description |
|---------|-------------|
| 🔤 **Sélection de police** | Choisissez parmi 3 polices intégrées (Noto Sans, Source Han Sans, Arial) ou toute police installée sur votre appareil |
| 📏 **Taille de police** | Ajustement de 80 % à 160 % avec un curseur |
| 🎨 **Couleur du texte** | Couleur de texte personnalisable avec le sélecteur de couleur |
| 🔗 **Couleur des liens** | Couleur des liens séparée pour une meilleure lisibilité |
| 🔄 **Application automatique** | Réapplique les réglages automatiquement à chaque visite sur un site configuré |
| 💾 **Sauvegarde automatique** | Les paramètres persistent automatiquement par site (5 sites max) |
| ↺ **Réinitialisation en un clic** | Restaurez les polices originales de la page instantanément |
| 🌍 **6 langues** | English, 中文, 日本語, Español, Deutsch, Français |

### ⭐ Pro (licence requise)

| Fonctionnalité | Description |
|---------|-------------|
| ♾️ **Configurations illimitées** | Enregistrez des réglages de police pour un nombre illimité de sites web |
| 📤 **Import / Export** | Sauvegardez et restaurez vos configurations de police entre appareils |

---

## Aperçu

<p align="center">
  <img src="icons/icon128.png" alt="Icône FontFixer" width="80">
</p>

---

## Navigateurs compatibles

| Navigateur | Statut |
|---------|--------|
| Google Chrome | ✅ Entièrement pris en charge |
| Microsoft Edge | ✅ Entièrement pris en charge |
| Autres navigateurs basés sur Chromium | ✅ Devrait fonctionner |

---

## Installation

1. Ouvrez la page des extensions de votre navigateur :
   - **Chrome** : `chrome://extensions/`
   - **Edge** : `edge://extensions/`
2. Activez le **mode Développeur** (bouton en haut à droite)
3. Cliquez sur **Charger le package décompressé** et sélectionnez le dossier `font-fixer`
4. Cliquez sur l'icône 🔤 FontFixer dans votre barre d'outils pour commencer

---

## Utilisation

### Changer les polices

1. Cliquez sur l'icône FontFixer dans votre barre d'outils
2. Sélectionnez une police dans le menu déroulant — 3 polices intégrées sont toujours disponibles ; cliquez sur **🔄** pour charger les polices installées sur votre appareil
3. Ajustez la taille de police avec le curseur (80 %–160 %)
4. Cochez optionnellement **Couleur du texte** / **Couleur des liens** pour remplacer les couleurs (désactivé = ne jamais toucher aux couleurs de la page)
5. Cliquez sur **Appliquer et enregistrer** — les paramètres s'appliquent instantanément et sont stockés pour ce site

### Application automatique

- Activez le commutateur **Application automatique** pour réappliquer automatiquement les réglages sauvegardés de ce site à chaque visite
- Avec l'application automatique désactivée, les paramètres ne s'appliquent que lorsque vous ouvrez le popup et cliquez sur **Appliquer et enregistrer**

### Réinitialisation

- Cliquez sur **Réinitialiser** pour supprimer les paramètres du site actuel et restaurer ses polices d'origine

---

## Fonctionnement

```
Sélection de la police et ajustement des paramètres
       ↓
Clic sur Appliquer et enregistrer
       ↓
CSS injecté via chrome.scripting.insertCSS
       ↓
Les polices de la page changent instantanément
       ↓
Paramètres sauvegardés dans chrome.storage.local
       ↓
(Application automatique activée) réappliqués automatiquement lors de votre prochaine visite
```

Tout le traitement des styles se fait en local dans votre navigateur. La seule requête réseau est **optionnelle** — quand vous activez une clé de licence Pro, FontFixer contacte le serveur de licences avec votre clé et des métadonnées basiques du navigateur (navigateur, langue, fuseau horaire). Aucun contenu de page web n'est lu ou envoyé.

**Note sur l'accès aux polices locales :** Les polices locales utilisent l'API Local Font Access — aucune permission de manifest n'est nécessaire. Chrome affiche une invite de permission à l'exécution, et l'API ne fonctionne que pendant un clic utilisateur. Ouvrez donc le popup et cliquez sur le **bouton 🔄 rafraîchir** pour charger vos polices locales. Seuls les noms d'affichage des polices sont lus — les fichiers source ne sont pas extraits, copiés ni envoyés. Vous pouvez révoquer l'autorisation à tout moment dans les paramètres du navigateur.

**Règle d'application automatique :** L'injection automatique de styles se fait par site. Activez le commutateur **Application automatique** dans le popup pour réappliquer les paramètres de ce site à chaque visite ; avec cette option désactivée, les paramètres ne s'appliquent que lorsque vous cliquez sur **Appliquer et enregistrer**.

---

## Avis relatif aux droits d'auteur des polices

Les trois typographies intégrées (Noto Sans, Source Han Sans, Arial) sont distribuées sous la licence SIL Open Font License, qui autorise l'usage personnel et commercial sans autorisation supplémentaire.

L'extension lit uniquement la liste des noms des polices installées sur votre appareil via l'API standard du navigateur, et n'extraiera, ne copiera ni n'enverra aucun fichier de police local. Tous les droits des polices système appartiennent à leurs titulaires respectifs.

---

## Confidentialité

- `storage` — Sauvegarde vos préférences de police en local. Aucun contenu de page web n'est stocké.
- `scripting` — Injecte du CSS pour changer les polices des pages. Ne lit pas le texte ni les données des pages.
- `activeTab` — N'accède à l'onglet actif que lorsque vous interagissez avec l'extension.
- `<all_urls>` — Permet à l'extension de réappliquer automatiquement vos styles de police sauvegardés sur les sites que vous avez configurés. Ne lit ni n'envoie jamais le contenu des pages.
- **Accès aux polices locales** — Aucune permission de manifest ; l'accès est accordé à l'exécution via une invite du navigateur. Lit uniquement les noms d'affichage, jamais les fichiers de police. Peut être révoqué à tout moment.
- Aucun suivi, aucun analytics. La seule requête réseau est l'activation/validation de la licence lorsque vous utilisez une clé de licence Pro.

---

## Avertissement relatif au droit d'auteur

Cette extension ajuste uniquement en local le style de rendu visuel des pages web pour une expérience de lecture confortable. Tous les droits d'auteur des textes, images et contenus des sites appartiennent à leurs éditeurs originaux. La modification du style d'affichage des pages ne confère aux utilisateurs aucun droit d'auteur sur le contenu des sites. Les utilisateurs doivent respecter les lois locales sur la propriété intellectuelle lors de la navigation.

---

## Licence

Copyright © 2026 FontFixer. Tous droits réservés.

---

## ❤️ Soutenir

Si FontFixer vous est utile, n'hésitez pas à soutenir le projet !

**[👉 Obtenir une clé de licence](https://www.annmax1983.com/checkout.html?plugin=fontfixer)**

---

> **Note :** Ce dépôt est destiné à la **présentation du projet uniquement**. Il ne contient pas le code source complet, le manifest, les icônes ou les scripts de build. Le code source complet ne sera **pas** publié ici.
