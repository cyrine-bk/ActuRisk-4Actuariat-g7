# 🏥 ActuRisk - Plateforme d'Assurance Santé en Microservices

## 📝 Description du Projet
**ActuRisk** est une plateforme d'assurance santé moderne conçue selon une architecture microservices. Face aux limites d'une architecture monolithique (couplage fort, scalabilité inefficace, blocages synchrones), ce projet propose un découpage métier basé sur le Domain-Driven Design (DDD). 

Le système est composé de 5 microservices autonomes, sécurisés par Keycloak et orchestrés via Docker Compose.

## 👥 Équipe & Rôles
**Classe / Groupe :** 4Actuariat - Groupe 7
*   **Racha Khammassi** : Responsable `billing-service` (MS1)
*   **Cyrine Boukhit** : Responsable `policy-service` (MS2)
*   **Mariem Cherif** : Responsable `claim-service` (MS3)
*   **Zeyneb Chouchene** : Responsable `risk-service` (MS4)
*   **Équipe** : Développement du `predictive-scoring-service` (MS5 - Commun)

## 🏗️ Architecture Globale
L'architecture repose sur les technologies suivantes :
*   **API Gateway** (Spring Cloud Gateway) pour le routage unique.
*   **Eureka** pour la découverte de services.
*   **Keycloak** pour la gestion des identités et des tokens JWT (OIDC).
*   **RabbitMQ** pour la communication asynchrone (Event-Driven).
*   **Docker & Docker Compose** pour la conteneurisation et le déploiement.

### Découpage des Microservices
| Microservice | Port | Base de données | Responsabilité principale |
| :--- | :--- | :--- | :--- |
| **billing-service** (MS1) | 8081 | MySQL | Gestion des cotisations, paiements et remboursements. |
| **policy-service** (MS2) | 8082 | PostgreSQL | Gestion des formules, garanties et contrats. |
| **claim-service** (MS3) | 8083 | PostgreSQL | Déclaration et instruction des sinistres. |
| **risk-service** (MS4) | 8084 | PostgreSQL | Gestion des profils de risque des assurés. |
| **predictive-scoring** (MS5)| 8085 | MongoDB | Moteur prédictif ML (FastAPI/Python) pour le calcul du score. |

## 📂 Structure du Dépôt
```text
ActuRisk-4Actuariat-g7/
|-- Backend/
|   |-- billing-service/        # MS1 (Spring Boot - MySQL)
|   |-- policy-service/         # MS2 (Spring Boot - PostgreSQL)
|   |-- claim-service/          # MS3 (Spring Boot - PostgreSQL)
|   |-- risk-service/           # MS4 (Spring Boot - PostgreSQL)
|   |-- predictive-scoring/     # MS5 (FastAPI Python - MongoDB)
|   |-- api-gateway/            # Spring Cloud Gateway
|   |-- eureka-server/          # Service Discovery
|-- Frontend/                   # Application cliente Web
|-- Documentation/
|   |-- Presentation/           # Support PPTX Séance 4
|   |-- Diagrams/               # Fichiers UML et Context Map
|-- README.md                   # Ce fichier
