# 📄 CV Builder — Créez votre CV professionnel en quelques minutes

> Une application web moderne pour créer, personnaliser et télécharger des CV professionnels, sans compétences en design requises.

---

## ✨ Aperçu

**CV Builder** est une plateforme intuitive qui permet à tout utilisateur de concevoir un CV élégant et professionnel en quelques étapes simples. Choisissez un template, remplissez vos informations, et téléchargez votre CV prêt à l'emploi.

### Fonctionnalités principales

- 🎨 **Templates prêts à l'emploi** — plusieurs modèles de CV modernes et professionnels
- ✏️ **Éditeur en temps réel** — prévisualisation instantanée des modifications
- 📥 **Export PDF** — téléchargement en un clic au format PDF
- 🔐 **Authentification utilisateur** — sauvegardez et retrouvez vos CVs
- 📱 **Interface responsive** — utilisable sur desktop et mobile

---

## 🛠️ Stack technique

| Couche           | Technologie                           |
| ---------------- | ------------------------------------- |
| Frontend         | React, Axios, React Router            |
| Backend          | Python, Django, Django REST Framework |
| Base de données  | PostgreSQL                            |
| Authentification | JWT (SimpleJWT)                       |
| Export PDF       | _A AJOUTER PLUS TARD_                 |
| Déploiement      | _A AJOUTER PLUS TARD_                 |

---

## 📁 Structure du projet

```
cv-builder/
├── backend/                  # Django + DRF
│   ├── config/               # Settings, URLs, WSGI
│   ├── users/                # Auth & gestion des utilisateurs
│   ├── resumes/              # Modèles, serializers, vues pour les CVs
│   ├── templates_cv/         # Gestion des templates disponibles
│   ├── requirements.txt
│   └── manage.py
│
├── frontend/                 # React
│   ├── public/
│   ├── src/
│   │   ├── components/       # Composants réutilisables (Header, Form, Preview...)
│   │   ├── pages/            # Pages principales (Home, Editor, Dashboard...)
│   │   ├── services/         # Appels API (axios)
│   │   ├── store/            # Gestion d'état (Context API ou Redux)
│   │   └── App.jsx
│   └── package.json
│
└── README.md
```

---

## 🚀 Installation et lancement

### Prérequis

- Python 3.10+
- Node.js 18+
- PostgreSQL

---

### Backend (Django)

```bash
# Cloner le projet
git clone https://github.com/ton-username/cv-builder.git
cd cv-builder/backend

# Créer et activer l'environnement virtuel
python -m venv env
source env/bin/activate  # Windows : env\Scripts\activate

# Installer les dépendances
pip install -r requirements.txt

# Configurer les variables d'environnement
cp .env.example .env
# Éditer .env avec vos paramètres (base de données, secret key, etc.)

# Appliquer les migrations
python manage.py migrate

# Lancer le serveur
python manage.py runserver
```

L'API sera disponible sur `http://localhost:8000/api/`

---

### Frontend (React)

```bash
cd ../frontend

# Installer les dépendances
npm install

# Configurer l'URL de l'API
cp .env.example .env
# REACT_APP_API_URL=http://localhost:8000/api

# Lancer l'application
npm run dev
```

L'interface sera disponible sur `http://localhost:5173`

---

## 🔌 Endpoints API principaux

| Méthode  | Endpoint                   | Description                      |
| -------- | -------------------------- | -------------------------------- |
| `POST`   | `/api/auth/register/`      | Inscription                      |
| `POST`   | `/api/auth/login/`         | Connexion (JWT)                  |
| `GET`    | `/api/resumes/`            | Lister les CVs de l'utilisateur  |
| `POST`   | `/api/resumes/`            | Créer un nouveau CV              |
| `GET`    | `/api/resumes/:id/`        | Détail d'un CV                   |
| `PUT`    | `/api/resumes/:id/`        | Mettre à jour un CV              |
| `DELETE` | `/api/resumes/:id/`        | Supprimer un CV                  |
| `GET`    | `/api/resumes/:id/export/` | Exporter en PDF                  |
| `GET`    | `/api/templates/`          | Lister les templates disponibles |

---

## ⚙️ Variables d'environnement

### Backend (`.env`)

```env
SECRET_KEY=your_django_secret_key
DEBUG=True
DATABASE_URL=postgresql://user:password@localhost:5432/cv_builder
ALLOWED_HOSTS=localhost,127.0.0.1
CORS_ALLOWED_ORIGINS=http://localhost:5173
```

### Frontend (`.env`)

```env
REACT_APP_API_URL=http://localhost:8000/api
```

---

## 🤝 Contribuer

Les contributions sont les bienvenues !

1. Forkez le dépôt
2. Créez une branche pour votre fonctionnalité (`git checkout -b feature/ma-fonctionnalite`)
3. Commitez vos changements (`git commit -m 'feat: ajout de ma fonctionnalité'`)
4. Poussez la branche (`git push origin feature/ma-fonctionnalite`)
5. Ouvrez une Pull Request

---

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

> Fait avec ❤️ — _Parce que tout le monde mérite un beau CV._
