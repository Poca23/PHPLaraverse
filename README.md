# PHPLaraverse

PHPLaraverse est une plateforme d'apprentissage moderne dédiée à PHP et Laravel 11, offrant un parcours structuré pour les développeurs débutants et intermédiaires.

## 🌟 Fonctionnalités

- 📚 Modules d'apprentissage progressifs pour PHP et Laravel
- 🧩 Exercices interactifs et validation en temps réel
- 🛠️ Mini-projets guidés pour appliquer les connaissances
- 🏆 Système de badges et suivi de progression
- 💬 Forum d'entraide communautaire
- 📱 Interface responsive adaptée à tous les appareils

## 🔧 Technologies

- **Framework:** Laravel 11
- **Frontend:** Blade + TailwindCSS + AlpineJS
- **Authentification:** Laravel Breeze
- **Administration:** Filament
- **Base de données:** SQLite (développement) / PostgreSQL (production)
- **Tests:** PHPUnit + Laravel Dusk
- **Déploiement:** Render

## 🚀 Installation

```bash
# Cloner le dépôt
git clone https://github.com/votre-username/PHPLaraverse.git

# Accéder au dossier
cd PHPLaraverse

# Installer les dépendances
composer install
npm install

# Configurer l'environnement
cp .env.example .env
php artisan key:generate

# Configurer la base de données dans .env puis migrer
php artisan migrate

# Compiler les assets
npm run dev

# Lancer le serveur
php artisan serve

📂 Structure du projet
Le projet est organisé en modules pour une meilleure séparation des fonctionnalités:

php-laraverse/
├── app/                   # Cœur de l'application
├── modules/               # Modules d'apprentissage
│   ├── PhpModule/        # Module d'apprentissage PHP
│   └── LaravelModule/    # Module d'apprentissage Laravel
├── resources/             # Assets, vues, etc.
└── ...

🌐 Environnement de développement
PHP 8.2+
Composer
Node.js & NPM
SQLite ou PostgreSQL
📝 Planning actuel
Le développement est organisé en 6 phases principales:

Conception et Préparation (Semaines 1-2)
Développement du Socle (Semaines 3-4)
Module PHP (Semaines 5-6)
Module Laravel (Semaines 7-8)
Expérience Utilisateur (Semaines 9-10)
Déploiement et Validation (Semaine 11)
🤝 Contribution
Bien que ce projet soit principalement développé comme un projet personnel, les suggestions et retours sont les bienvenus.

📝 Licence
Ce projet est sous licence MIT.