---
name: search-alt-developpeur-frontend
description: Search fresh direct-company frontend developer apprenticeship jobs in Paris/Ile-de-France from a CV, filtering training-center noise and scoring UI/product/frontend match.
license: MIT
compatibility: opencode
metadata:
    audience: job-seekers
    workflow: job-search
---

## What I Do

- Analyse un CV de developpeur frontend pour extraire les forces UI, React/Vue/Angular, TypeScript, integration et qualite produit.
- Recherche des offres d'alternance frontend recentes en entreprise directe a Paris et en Ile-de-France.
- Filtre agressivement le bruit des ecoles, centres de formation et fausses alternances.
- Score les offres selon la qualite frontend reelle, la fraicheur, la stack UI et l'alignement avec le CV.
- Produit un tableau de bord actionnable avec coaching de candidature.

## When To Use Me

Use this when the user wants to find frontend developer apprenticeship jobs, especially after sharing a CV or asking for fresh alternance frontend offers in Paris or Ile-de-France.

CV files are usually stored in `/home/ehoura/Documents/`, but the user will specify the exact CV path to use for each run. Ask for the CV path if it is not provided; do not guess which CV to use. If live web search is unavailable, ask the user for job-board URLs or offer links to evaluate.

## Process

1. **Trigger CV**

Analyse the CV first. Extract:

- Frontend frameworks: React, Next.js, Vue, Nuxt, Angular, Svelte.
- Language and tooling: TypeScript, JavaScript, Vite, Webpack, ESLint, Prettier, package managers.
- Styling and design systems: CSS, Sass, Tailwind, CSS modules, styled-components, component libraries, responsive design.
- Product UI skills: accessibility, forms, validation, routing, state management, performance, animations, UX quality.
- API integration: REST, GraphQL, fetch/axios, auth flows, client-side caching, error/loading states.
- Quality and delivery: tests, Storybook, Playwright, Cypress, CI/CD, Vercel, Netlify.

Completion criterion: the candidate's strongest UI/framework/integration/testing stack and weak spots are explicitly known before searching or scoring.

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

Reject the offer if the description does not explicitly mention frontend responsibility:

- UI, interface, web app, pages, components, integration, responsive design, accessibility, frontend performance, design system, client-side state.

Reject the offer if it is only:

- Backend work with no UI responsibility.
- WordPress/no-code content editing with no frontend engineering.
- Graphic design, community management, marketing, webmaster-only, QA-only, or support-only.

Completion criterion: no retained offer comes from a blocked source, contains a false-alternance marker, or lacks explicit frontend engineering work.

4. **Score Match**

Score each retained offer out of 10:

- +2 for clear UI/component/frontend feature responsibility.
- +2 for modern frontend framework work such as React, Next.js, Vue, Nuxt, Angular or Svelte.
- +1 for TypeScript or strong JavaScript engineering.
- +1 for API integration, auth flows, forms, validation, client-side state or data fetching.
- +1 for responsive design, accessibility, design system, UX polish or performance.
- +1 for tests, Storybook, Playwright, Cypress, CI/CD, Vercel or Netlify.
- +1 for strong CV alignment with the required frontend stack.
- +1 for a direct company posting with concrete product/team context.

Cap at 10. Penalize vague listings, generic missions, missing stack details, marketing-heavy roles, or school-like wording even if they pass the hard rejects.

5. **Classify Frontend Depth**

For each retained offer, classify frontend depth:

- **UI-heavy**: components, pages, styling, responsive design and polish dominate.
- **Integration-heavy**: API integration, auth, state management and data fetching dominate.
- **Design-system-heavy**: reusable components, Storybook, accessibility and design consistency dominate.
- **Product frontend**: balanced UI, integration and product feature delivery.

Compare the depth with the CV projects and identify the best application angle.

6. **If Results Are Weak**

If no valid offer under 2 days is found, do not fill the dashboard with weak matches. Say that no strict match was found and propose exactly one of these next moves:

- Expand freshness to 5 days.
- Split the search by frontend stack, such as React/Next.js, Vue/Nuxt, Angular, or TypeScript UI.

## Obsidian Persistence

When file tools are available, persist the useful results in the user's Obsidian vault instead of only returning them in chat.

- Application notes go in `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Candidatures/`.
- Search reports go in `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Recherches/`.
- Obsidian templates are stored only in `/home/ehoura/Documents/Le Coffre d'Yvann/__Models/`.
- Use `/home/ehoura/Documents/Le Coffre d'Yvann/__Models/Modèle - Candidature.md` as the application-note structure.
- Do not create templates inside the `Emploi` folder.
- For every search run, create a markdown report in `Recherches/` named `YYYY-MM-DD - Recherche frontend.md`.
- Include the exact CV path used in the search report.
- Do not copy the CV into the `Emploi` folder unless the user explicitly asks for it.
- After creating or updating application notes, run `/home/ehoura/Documents/Le Coffre d'Yvann/CAPS(Autre Responsabilités)/Emploi/Automatisation/generer-canvas.sh` if available, so `Vue emploi.canvas` reflects the current pipeline.

For each retained offer, create or update one markdown note using this filename pattern:

`YYYY-MM-DD - Entreprise - Poste.md`

Use these YAML fields for frontend results:

```yaml
type: candidature
entreprise: ""
poste: ""
lien_offre: ""
source: ""
axe_recherche: "Frontend"
score_match: 0
stack: ""
profondeur: ""
publie_il_y_a: ""
source_skill: "search-alt-developpeur-frontend"
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

| Poste & Entreprise        | Publie il y a | Score Match | Stack Frontend (Framework / Langage / UI / Tests) | Profondeur                                                           | Lien de l'offre |
| ------------------------- | ------------- | ----------- | ------------------------------------------------- | -------------------------------------------------------------------- | --------------- |
| [Poste] chez [Entreprise] | X jour(s)     | 0/10        | Ex: React / TypeScript / Tailwind / Playwright    | UI-heavy, Integration-heavy, Design-system-heavy ou Product frontend | [Lien direct]   |

Then add a short coaching section:

- **Meilleure cible**: the highest-confidence offer and why.
- **Angle CV**: what to emphasize from the CV for that offer.
- **Risque**: any gap or ambiguity to handle in the application.
- **Message d'approche**: a concise message the candidate can adapt.

## Quality Bar

- Prefer fewer high-confidence offers over many noisy ones.
- Never include school-placement listings or financing funnels.
- Never infer frontend scope from the title alone; the description must prove UI, component or client-side responsibility.
- Keep direct links and source dates visible so the user can verify quickly.
