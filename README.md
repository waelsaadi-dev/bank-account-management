# 🏦 E-Banking Backend

Une application backend développée avec **Spring Boot** permettant la gestion des clients et de leurs comptes bancaires.  
Elle offre des fonctionnalités telles que la création de clients, la gestion des comptes, ainsi que les opérations bancaires (dépôts, retraits, transferts).  

## 🚀 Fonctionnalités

- **Gestion des clients**  
  - Créer, modifier, supprimer un client  
  - Consulter la liste des clients  
  - Rechercher un client par identifiant ou critères  

- **Gestion des comptes bancaires**  
  - Consulter la liste des comptes  
  - Consulter le détail d’un compte et ses opérations  
  - Effectuer des dépôts et retraits  
  - Visualiser l’historique des transactions (pagination disponible)

## 📌 Architecture du projet

src/main/java/org/sid/ebankingbackend
├── dtos # Objets de transfert de données (DTOs)
├── entities # Entités JPA (Customer, BankAccount, Operation, etc.)
├── enums # Types énumérés (AccountStatus, OperationType, etc.)
├── exceptions # Gestion des exceptions personnalisées
├── mappers # MapStruct pour convertir Entities ↔ DTOs
├── repositories # Interfaces JPA Repository
├── services # Logique métier
└── web # Contrôleurs REST (APIs exposées) 



## 🛠️ Technologies utilisées

- **Spring Boot 3**
- **Spring Data JPA** (Hibernate)
- **Spring Web**
- **Spring Validation**
- **Swagger / OpenAPI** pour la documentation
- **H2 Database** (pour les tests, peut être remplacée par MySQL/PostgreSQL)
- **Lombok** pour réduire le code boilerplate

## 📖 Documentation API

L’API est documentée via **Swagger**.  
Démarrez l’application puis accédez à :

👉 [http://localhost:8085/swagger-ui.html](http://localhost:8085/swagger-ui.html)

### Endpoints principaux

#### 👤 Customer REST API
- `GET /customers` → Liste de tous les clients  
- `POST /customers` → Créer un nouveau client  
- `GET /customers/{id}` → Détails d’un client  
- `PUT /customers/{customerId}` → Modifier un client  
- `DELETE /customers/{id}` → Supprimer un client  
- `GET /customers/search` → Rechercher un client  

#### 💳 Bank Account REST API
- `GET /accounts` → Liste des comptes  
- `GET /accounts/{accountId}` → Détails d’un compte  
- `POST /accounts/debit` → Effectuer un retrait  
- `POST /accounts/credit` → Effectuer un dépôt  
- `GET /accounts/{accountId}/operations` → Historique des opérations  
- `GET /accounts/{accountId}/pageOperations` → Historique paginé  

## ▶️ Lancement du projet

1. Cloner le projet
```bash
git clone https://github.com/votre-repo/ebanking-backend.git
cd ebanking-backend

2. Compiler et exécuter
bash
Copier
Modifier
./mvnw spring-boot:run
ou avec Maven installé :

bash
Copier
Modifier
mvn spring-boot:run
3. Accéder à l’application
API Swagger : http://localhost:8085/swagger-ui.html

Base H2 : http://localhost:8085/h2-console

📦 Exemple JSON
Création d’un client
json
Copier
Modifier
{
  "name": "Jean Dupont",
  "email": "jean.dupont@example.com"
}
Dépôt sur un compte
json
Copier
Modifier
{
  "accountId": "12345",
  "amount": 1000,
  "description": "Dépôt salaire"
}
Retrait sur un compte
json
Copier
Modifier
{
  "accountId": "12345",
  "amount": 200,
  "description": "Retrait distributeur"
}
📌 Améliorations futures
Ajout de l’authentification (Spring Security + JWT)

Implémentation d’un module de transfert entre comptes

Gestion multi-devises

Mise en place de tests unitaires et d’intégration
