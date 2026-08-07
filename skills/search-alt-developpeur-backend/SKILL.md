---
name: search-alt-developpeur-backend
description: Search fresh direct-company backend developer apprenticeship jobs in Paris/Ile-de-France from a CV, filtering training-center noise and scoring API/data/ops match.
license: MIT
compatibility: opencode
metadata:
    audience: job-seekers
    workflow: job-search
---

## What I Do

- Analyse un CV de developpeur backend pour extraire les forces API, data, securite, tests et deploiement.
- Recherche des offres d'alternance backend recentes en entreprise directe a Paris et en Ile-de-France.
- Filtre agressivement le bruit des ecoles, centres de formation et fausses alternances.
- Score les offres selon la qualite backend reelle, la fraicheur, la stack serveur et l'alignement avec le CV.
- Produit un tableau de bord actionnable avec coaching de candidature.

## When To Use Me

Use this when the user wants to find backend developer apprenticeship jobs, especially after sharing a CV or asking for fresh alternance backend offers in Paris or Ile-de-France.

CV files are usually stored in `/home/ehoura/Documents/`, but the user will specify the exact CV path to use for each run. Ask for the CV path if it is not provided; do not guess which CV to use. If live web search is unavailable, ask the user for job-board URLs or offer links to evaluate.

## Process

1. **Trigger CV**

Analyse the CV first. Extract:

- Backend languages: Node.js, TypeScript, Python, PHP, Java, Go, C#, Ruby.
- Backend frameworks: NestJS, Express, Fastify, Django, FastAPI, Symfony, Laravel, Spring Boot, .NET.
- API layer: REST, GraphQL, webhooks, validation, serialization, OpenAPI, versioning.
- Data layer: PostgreSQL, MySQL, MongoDB, Redis, Prisma, TypeORM, Sequelize, SQL, indexing.
- Security and identity: JWT, OAuth, sessions, RBAC, permissions, authentication, authorization.
- Reliability and delivery: tests, Docker, CI/CD, queues, workers, cron jobs, monitoring, cloud deployment.

Completion criterion: the candidate's strongest backend/API/data/ops stack and weak spots are explicitly known before searching or scoring.

2. **Search Scope**

Search only for:

- Location: Paris and Ile-de-France.
- Contract: alternance only.
- Employer type: direct company only, not school-led placement.
- Freshness: offers published 2 days ago or less.

Completion criterion: every retained offer has a visible publication date within 5 days, a Paris/Ile-de-France location, and an alternance contract.

3. **Hard Rejects**

Reject the offer immediately if it matches any blocked source:

- ISCOD
- Studi
- GGE
- OpenClassrooms
- MyDigitalSchool
- ESG
- Eureka Education
- Efrei
- Epitech
- Rocket School
- Holberton
- Wild Code School
- IronHack
- Le Wagon

Reject the offer immediately if it contains any false-alternance marker:

- "Aide au financement"
- "Rythme 1j/4j"
- "Diplome vise"
- "Nous recherchons pour notre ecole partenaire"

Reject the offer if the description does not explicitly mention backend responsibility:

- API, backend, server, services, database, authentication, authorization, data processing, integrations, workers, infrastructure.

Reject the offer if it is only:

- Frontend integration with no server responsibility.
- WordPress/no-code maintenance with no backend engineering.
- Generic IT support, helpdesk, webmaster, QA-only, data-only, or devops-only.

Completion criterion: no retained offer comes from a blocked source, contains a false-alternance marker, or lacks explicit backend engineering work.

4. **Score Match**

Score each retained offer out of 10:

- +2 for clear API/backend service responsibility.
- +2 for database, SQL/NoSQL, persistence, or data-modeling responsibility.
- +1 for authentication, authorization, security, or permissions.
- +1 for tests, code quality, architecture, or maintainability.
- +1 for deployment, Docker, CI/CD, cloud, queues, workers, or production operations.
- +1 for strong CV alignment with the required backend stack.
- +1 for modern backend stack such as NestJS, FastAPI, TypeScript, Prisma, PostgreSQL, Docker, Kafka, Redis.
- +1 for a direct company posting with concrete product/team context.

Cap at 10. Penalize vague listings, generic missions, missing stack details, or school-like wording even if they pass the hard rejects.

5. **Classify Backend Depth**

For each retained offer, classify backend depth:

- **API-heavy**: endpoints, integrations and service logic dominate.
- **Data-heavy**: schema, SQL, persistence, analytics pipelines or data quality dominate.
- **Ops-heavy**: deployment, Docker, CI/CD, monitoring, infra or production reliability dominate.
- **Product backend**: balanced API, data and product feature delivery.

Compare the depth with the CV projects and identify the best application angle.

6. **If Results Are Weak**

If no valid offer under 2 days is found, do not fill the dashboard with weak matches. Say that no strict match was found and propose exactly one of these next moves:

- Expand freshness to 5 days.
- Split the search by backend stack, such as Node/NestJS, Python/FastAPI, PHP/Symfony, or Java/Spring.

## Obsidian Persistence

When file tools are available, persist the useful results in the user's Obsidian vault instead of only returning them in chat.

- Application notes go in `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Candidatures/`.
- Search reports go in `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Recherches/`.
- Obsidian templates are stored only in `/home/ehoura/Documents/Le Coffre d'Yvann/__Models/`.
- Use `/home/ehoura/Documents/Le Coffre d'Yvann/__Models/Modèle - Candidature.md` as the application-note structure.
- Do not create templates inside the `Emploi` folder.
- For every search run, create a markdown report in `Recherches/` named `YYYY-MM-DD - Recherche backend.md`.
- Include the exact CV path used in the search report.
- Do not copy the CV into the `Emploi` folder unless the user explicitly asks for it.
- After creating or updating application notes, run `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Automatisation/generer-canvas.sh` if available, so `Vue emploi.canvas` reflects the current pipeline.

For each retained offer, create or update one markdown note using this filename pattern:

`YYYY-MM-DD - Entreprise - Poste.md`

Use these YAML fields for backend results:

```yaml
type: candidature
entreprise: ""
poste: ""
lien_offre: ""
source: ""
axe_recherche: "Backend"
score_match: 0
stack: ""
profondeur: ""
publie_il_y_a: ""
source_skill: "search-alt-developpeur-backend"
lieu: "Paris / Ile-de-France"
teletravail: ""
salaire: ""
statut: "À préparer"
priorite: "Moyenne"
date_decouverte: YYYY-MM-DD
date_candidature: 
date_derniere_action: YYYY-MM-DD
prochaine_relance: 
contact_nom: ""
contact_email: ""
tags:
  - emploi
```

If no reliable offer is retained, create only a search report in `Recherches/`; do not create weak application notes.

## Output Format

Return a dashboard first:

| Poste & Entreprise        | Publie il y a | Score Match | Stack Backend (Langage / Framework / DB / Ops) | Profondeur                                          | Lien de l'offre |
| ------------------------- | ------------- | ----------- | ---------------------------------------------- | --------------------------------------------------- | --------------- |
| [Poste] chez [Entreprise] | X jour(s)     | 0/10        | Ex: TypeScript / NestJS / PostgreSQL / Docker  | API-heavy, Data-heavy, Ops-heavy ou Product backend | [Lien direct]   |

Then add a short coaching section:

- **Meilleure cible**: the highest-confidence offer and why.
- **Angle CV**: what to emphasize from the CV for that offer.
- **Risque**: any gap or ambiguity to handle in the application.
- **Message d'approche**: a concise message the candidate can adapt.

## Quality Bar

- Prefer fewer high-confidence offers over many noisy ones.
- Never include school-placement listings or financing funnels.
- Never infer backend scope from the title alone; the description must prove server, API or data responsibility.
- Keep direct links and source dates visible so the user can verify quickly.
