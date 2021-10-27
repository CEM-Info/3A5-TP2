# Plan de test 1 (exemple)

**Auteur:** Vincent Carrier

**Description:** Exécution du script Import-Users.ps1

**Préconditions:** L'utilisateur courant est administrateur du système et sa console PowerShell est élevée en tant qu'admin

| ID | Cas de test                             | Étape | Description                                          | Résultat attendu                                                          | Résultat obtenu | Commentaire |
|---:|-----------------------------------------|---|----------------------------------------------------------|---------------------------------------------------------------------------|------------|------------------|
| TC01  | Importer liste d'utilisateurs           | 1 | $newusers = Import-LocalUser.ps1 -Path ".\\users.csv"    | Le script s'exécute sans erreur                                           | Succès     |                  |
|      |                                         | 2 | $newusers                                                | Retourne la liste des utilisateurs: arobe, bgrat, ctrem, ctrem1, ddeni    | Échec      | Il manque ctrem1 |
|      |                                         | 3 | $newusers | Get-Member                                   | Le type est LocalUser                                                     | Succès     |                  |
|      |                                         | 4 | Get-LocalUser                                            | Les 5 utilisateurs sont dans la liste: arobe, bgrat, ctrem, ctrem1, ddeni | Échec      | Il manque ctrem1 |
| TC02  | Démarrer une session avec arobe         | 1 | Démarrer une session avec arobe, mot de passe ALro132435 | La session est démarrée avec succès                                       | Succès     |                  |
|      |                                         | 2 | Modifier le mot de passe                                 | Le mot de passe est changé avec succès                                    | Succès     |                  |

