---
name: search-alt-developpeur-fullstack
description: Search fresh direct-company fullstack developer apprenticeship jobs in Paris/Ile-de-France from a CV, filtering training-center noise and scoring front/back/ops match.
license: MIT
compatibility: opencode
metadata:
    audience: job-seekers
    workflow: job-search
---

## What I Do

- Agis comme un expert sourcing fullstack alternance, avec un filtrage renforcé car ce profil est très pollué par les centres de formation.
- Analyse un CV de développeur fullstack pour extraire les forces Front, Back, API, base de données et déploiement.
- Recherche des offres d'alternance fullstack récentes en entreprise directe à Paris et en Île-de-France.
- Filtre agressivement le bruit des écoles, centres de formation et fausses alternances.
- Score les offres selon la stack complète, la fraîcheur, le niveau fullstack réel et l'alignement avec le CV.
- Produit un tableau de bord actionnable avec coaching de candidature.

## When To Use Me

Use this when the user wants to find fullstack developer apprenticeship jobs, especially after sharing a CV or asking for fresh alternance offers in Paris or Île-de-France.

Execution starts when the user provides CV content or the exact CV file path. CV files are usually stored in `/home/ehoura/Documents/`, but the user will specify the exact CV path to use for each run. Ask for the CV path if it is not provided; do not guess which CV to use. If live web search is unavailable, ask the user for job-board URLs or offer links to evaluate.

## Process

1. **Protocole de Démarrage / Trigger CV**

Analyse the CV first. Extract:

- Frontend technologies: React, Next.js, Vue, Nuxt, Angular, TypeScript, Tailwind, state management.
- Backend technologies: Node.js, NestJS, Express, Adonis.js, Python, Django, FastAPI, PHP, Symfony, Java, Spring.
- Data layer: PostgreSQL, MySQL, MongoDB, Redis, Prisma, ORM usage.
- Fullstack glue: REST, GraphQL, authentication, JWT, OAuth, authorization, API design, validation.
- Ops and delivery: Docker, Kubernetes, Docker Swarm, CI/CD, GitHub Actions, Vercel, Netlify, Heroku, Azure, cloud, monitoring, deployment.

Also identify:

- The complementarity between frontend and backend technologies, such as React/Vue/Nuxt on the client side and Node.js/Python/FastAPI/Django on the server side.
- The transversal skills that bind the stack together: REST/GraphQL APIs, state management, authentication, authorization and deployment.

Completion criterion: the candidate's strongest Front/Back/DB/Ops stack, transversal glue skills and weak spots are explicitly known before searching or scoring.

2. **Paramètre de Fraîcheur Stricte / Search Scope**

Search only for:

- Location: Paris and Île-de-France.
- Contract: alternance only.
- Employer type: direct company only, not school-led placement.
- Freshness: offers published 2 days ago or less (≤ 5j).

Completion criterion: every retained offer has a visible publication date within 5 days, a Paris/Île-de-France location, an alternance contract and a direct-company source.

3. **Filtrage Sémantique & Anti-Bruit / Hard Rejects**

Reject the offer immediately if it matches any blocked source:

- ISCOD
- Studi
- GGE
- OpenClassrooms
- MyDigitalSchool
- ESG
- Eureka Éducation
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
- "Diplôme visé"
- "Nous recherchons pour notre école partenaire"

Reject the offer if the description does not explicitly mention real responsibility on both sides of the application:

- Client side: UI, frontend, pages, components, user interface, web app.
- Server side: API, backend, database, services, authentication, server logic.

Completion criterion: no retained offer comes from a blocked source, contains a false-alternance marker, or describes only frontend or only backend work.

4. **Intelligence de Matching / Score Match**

Score each retained offer out of 10:

- +2 for a clear frontend responsibility.
- +2 for a clear backend responsibility.
- +1 for database or persistence work.
- +1 for API/authentication work.
- +1 for deployment, Docker, CI/CD, cloud, or production delivery.
- +1 for strong CV alignment with the required stack.
- +1 for modern fullstack or architecture stack such as Next.js, NestJS, TypeScript, Prisma, GraphQL, Docker, Kubernetes, Azure or CI/CD.
- +1 for a direct company posting with concrete product/team context.

Cap at 10. Penalize vague listings, generic missions, missing stack details, or school-like wording even if they pass the hard rejects.

5. **Équilibre de Profil / Classify Balance**

For each retained offer, classify the technical balance:

- **Front-heavy**: frontend dominates and backend is secondary.
- **Back-heavy**: backend/API/data dominates and frontend is secondary.
- **Balanced fullstack**: meaningful responsibilities exist across frontend, backend and data/API layers.

Compare the balance with the CV projects and identify the best angle for the application. If the offer mentions modern architecture technologies such as Next.js, NestJS, TypeScript, Docker, Kubernetes, Azure or CI/CD, explicitly mention how to value them in the application coaching.

6. **If Results Are Weak**

If no valid fullstack offer under 2 days or less(1) is found, do not fill the dashboard with weak matches. Say that no strict match was found and propose these next moves:

- Expand freshness to 5 days.
- Split the search into frontend alternance and backend alternance searches.

## Obsidian Persistence

When file tools are available, persist the useful results in the user's Obsidian vault instead of only returning them in chat.

- Application notes go in `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Candidatures/`.
- Search reports go in `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Recherches/`.
- Obsidian templates are stored only in `/home/ehoura/Documents/Le Coffre d'Yvann/__Models/`.
- Use `/home/ehoura/Documents/Le Coffre d'Yvann/__Models/Modèle - Candidature.md` as the application-note structure.
- Do not create templates inside the `Emploi` folder.
- For every search run, create a markdown report in `Recherches/` named `YYYY-MM-DD - Recherche fullstack.md`.
- Include the exact CV path used in the search report.
- Do not copy the CV into the `Emploi` folder unless the user explicitly asks for it.
- After creating or updating application notes, run `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Automatisation/generer-canvas.sh` if available, so `Vue emploi.canvas` reflects the current pipeline.

For each retained offer, create or update one markdown note using this filename pattern:

`YYYY-MM-DD - Entreprise - Poste.md`

Use these YAML fields for fullstack results:

```yaml
type: candidature
entreprise: ""
poste: ""
lien_offre: ""
source: ""
axe_recherche: "Fullstack"
score_match: 0
stack: ""
profondeur: ""
publie_il_y_a: ""
source_skill: "search-alt-developpeur-fullstack"
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

| Poste & Entreprise        | Publié il y a | Score Match | Stack Complète (Front / Back / DB) | Équilibre                           | Lien de l'offre |
| ------------------------- | ------------- | ----------- | ---------------------------------- | ----------------------------------- | --------------- |
| [Poste] chez [Entreprise] | X jour(s)     | 0/10        | Ex: Vue.js / Go / PostgreSQL       | Front-heavy, Back-heavy ou Balanced | [Lien direct]   |

Then add a short coaching section:

- **Meilleure cible**: the highest-confidence offer and why.
- **Angle CV**: what to emphasize from the CV for that offer.
- **Risque**: any gap or ambiguity to handle in the application.
- **Message d'approche**: a concise message the candidate can adapt.

## Quality Bar

- Prefer fewer high-confidence offers over many noisy ones.
- Never include school-placement listings or financing funnels.
- Never infer fullstack scope from the title alone; the description must prove client and server responsibility.
- Keep direct links and source dates visible so the user can verify quickly.
