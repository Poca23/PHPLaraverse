# Modèle Conceptuel de Données - PHPLaraverse

## Entités principales

### User (Utilisateur)
- id (PK)
- name (nom complet)
- email (adresse email unique)
- password (mot de passe hashé)
- role (enum: 'admin', 'student')
- avatar (chemin vers l'image de profil, facultatif)
- created_at (date de création)
- updated_at (date de mise à jour)

### Module
- id (PK)
- name (nom du module: "PHP" ou "Laravel")
- slug (identifiant URL)
- description (description du module)
- icon (icône représentative)
- order (ordre d'affichage)
- is_active (boolean)
- created_at
- updated_at

### Chapter (Chapitre)
- id (PK)
- module_id (FK)
- title (titre du chapitre)
- slug (identifiant URL)
- description (description du chapitre)
- order (ordre dans le module)
- created_at
- updated_at

### Lesson (Leçon)
- id (PK)
- chapter_id (FK)
- title (titre de la leçon)
- slug (identifiant URL)
- content (contenu HTML/Markdown)
- order (ordre dans le chapitre)
- estimated_time (durée estimée en minutes)
- created_at
- updated_at

### Exercise (Exercice)
- id (PK)
- lesson_id (FK)
- title (titre de l'exercice)
- instructions (consignes)
- starter_code (code de départ)
- expected_result (résultat attendu)
- hint (indice, facultatif)
- created_at
- updated_at

### Quiz
- id (PK)
- chapter_id (FK)
- title (titre du quiz)
- description (description du quiz)
- min_score_to_pass (score minimum pour réussir)
- created_at
- updated_at

### QuizQuestion (Question de Quiz)
- id (PK)
- quiz_id (FK)
- question (texte de la question)
- type (enum: 'multiple_choice', 'true_false', 'code')
- created_at
- updated_at

### QuizOption (Option de réponse)
- id (PK)
- question_id (FK)
- content (texte de l'option)
- is_correct (boolean)
- created_at
- updated_at

### UserProgress (Progression utilisateur)
- id (PK)
- user_id (FK)
- lesson_id (FK)
- status (enum: 'not_started', 'in_progress', 'completed')
- completed_at (date de complétion)
- created_at
- updated_at

### ExerciseSubmission (Soumission d'exercice)
- id (PK)
- user_id (FK)
- exercise_id (FK)
- submitted_code (code soumis)
- is_correct (boolean)
- feedback (retour automatique)
- submitted_at (date de soumission)
- created_at
- updated_at

### QuizResult (Résultat de quiz)
- id (PK)
- user_id (FK)
- quiz_id (FK)
- score (score obtenu)
- passed (boolean)
- completed_at (date de complétion)
- created_at
- updated_at

### Badge (Badge)
- id (PK)
- name (nom du badge)
- description (description)
- image (chemin vers l'image)
- required_progress (progrès requis pour l'obtention)
- created_at
- updated_at

### UserBadge (Badges des utilisateurs)
- id (PK)
- user_id (FK)
- badge_id (FK)
- earned_at (date d'obtention)
- created_at
- updated_at

### ForumTopic (Sujet du forum)
- id (PK)
- user_id (FK)
- title (titre du sujet)
- content (contenu)
- status (enum: 'open', 'resolved', 'closed')
- created_at
- updated_at

### ForumPost (Message du forum)
- id (PK)
- topic_id (FK)
- user_id (FK)
- content (contenu du message)
- created_at
- updated_at

### Favorite (Favori)
- id (PK)
- user_id (FK)
- lesson_id (FK)
- created_at
- updated_at

## Relations principales

1. User (1) - UserProgress (N)
2. User (1) - ExerciseSubmission (N)
3. User (1) - QuizResult (N)
4. User (1) - UserBadge (N)
5. User (1) - Favorite (N)
6. User (1) - ForumTopic (N)
7. User (1) - ForumPost (N)
8. Module (1) - Chapter (N)
9. Chapter (1) - Lesson (N)
10. Chapter (1) - Quiz (N)
11. Lesson (1) - Exercise (N)
12. Lesson (1) - UserProgress (N)
13. Lesson (1) - Favorite (N)
14. Quiz (1) - QuizQuestion (N)
15. QuizQuestion (1) - QuizOption (N)
16. Quiz (1) - QuizResult (N)
17. Exercise (1) - ExerciseSubmission (N)
18. Badge (1) - UserBadge (N)
19. ForumTopic (1) - ForumPost (N)
