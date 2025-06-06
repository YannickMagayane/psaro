# Hyper Psaro - E-commerce alimentaire en ligne

---

## Présentation

Hyper Psaro est une application web e-commerce de vente en ligne de produits alimentaires, développée dans le cadre d’un projet académique selon la méthode UP (Unified Process). Le site permet aux clients de commander leurs produits alimentaires favoris avec un panier façon Amazon, profiter des promotions, filtrer les produits facilement et bénéficier d’une interface moderne, responsive et agréable.

Cette application est inspirée du supermarché Hyper Psaro à Lubumbashi et vise à offrir une expérience utilisateur professionnelle avec une simulation de paiement et un reçu imprimable.

---

## Technologies utilisées

- **Backend** : Django (Python 3.11+)
- **Frontend** : HTML5 + Tailwind CSS 3.x
- **Base de données** : SQLite (configurable PostgreSQL)
- **Gestion des utilisateurs** : Django auth
- **Migrations** : Django migrations
- **Templates** : Django Templates avec composants réutilisables
- **Simulation paiement** : Backend Django
- **Envoi email** : Django Email (console backend pour dev)
- **Développement** : VSCode, Git

---

## Fonctionnalités principales

### 1. Authentification & Inscription

- Inscription et connexion sécurisée des clients et administrateurs.
- Super utilisateur Django a accès au dashboard d’administration complet.
- Permissions spécifiques : seul le superuser peut accéder à la gestion CRUD des produits, commandes, utilisateurs.

### 2. Page d’accueil

- Bannières promotionnelles dynamiques.
- Sélection de produits en promotion affichés sur la page.
- Présentation claire des catégories.

### 3. Catalogue produits

- Affichage par catégories et sous-catégories.
- Recherche intelligente avec filtres avancés : prix, catégorie, nouveautés, promotions.
- Fiche produit détaillée avec images, description complète, prix, stock disponible.
- Ajout au panier rapide façon Amazon (sans rechargement complet).

### 4. Panier d’achat (Amazon style)

- Ajout, modification, suppression de produits dans le panier en temps réel.
- Vue récapitulative avec quantités, sous-totaux, total.
- Interface moderne, claire et responsive.
- Possibilité de sauvegarder panier et historique.

### 5. Validation de commande

- Formulaire de validation complet avec adresse de livraison, coordonnées.
- Simulation de paiement intégrée (paiement fictif).
- Génération d’un reçu imprimable en PDF.
- Envoi de notification email à la commande (simulation).

### 6. Gestion administrative

- Dashboard admin réservé au superuser.
- CRUD complet sur produits, catégories, commandes et utilisateurs.
- Visualisation des commandes en cours, livrées, annulées.
- Gestion des promotions.

### 7. Historique des commandes clients

- Visualisation simple des commandes passées.
- Statut de la commande (en attente, en cours, livrée).

### 8. Système de livraison

- Gestion des zones de livraison.
- Suivi du statut de livraison par client et admin.

### 9. Design et UX/UI

- Design moderne, épuré, inspiré des meilleures pratiques ecommerce 2024.
- Responsive (mobile, tablette, desktop).
- Utilisation intensive de Tailwind CSS pour la rapidité et la cohérence.
- Composants réutilisables : header, footer, sidebar, cards produit.
- Feedback visuel interactif (animations, notifications).

---

## Modules et librairies recommandés

| Module Django               | Rôle                                   |
|----------------------------|---------------------------------------|
| `django`                   | Framework principal                    |
| `django-crispy-forms`      | Formulaires stylés avec Tailwind      |
| `django-filter`            | Filtrage avancé pour catalogues       |
| `django-allauth`           | Authentification & gestion utilisateurs|
| `weasyprint`               | Génération de PDF (reçu imprimable)  |
| `django-taggit`            | Gestion des tags pour produits        |
| `Pillow`                   | Gestion images produits                |

---

## Installation et lancement

### Prérequis

- Python 3.11+
- Virtualenv (recommandé)
- Git

### Étapes

```bash
git clone https://github.com/tonpseudo/hyper-psaro.git
cd hyper-psaro
python -m venv env
source env/bin/activate  # sur Windows: env\Scripts\activate
pip install -r requirements.txt

# Appliquer les migrations
python manage.py migrate

# Charger fixtures de test
python manage.py loaddata fixtures/products.json
python manage.py loaddata fixtures/users.json

# Créer super utilisateur
python manage.py createsuperuser

# Lancer le serveur
python manage.py runserver
