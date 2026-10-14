# Pattynologies

Pattynologies is the public home for this organization's software.

- [pattynologies.com](https://pattynologies.com)
- [Learn](https://github.com/pattynologies/learn) — small AWS lessons, one step at a time
- [Mikepattyn.Email](https://github.com/pattynologies/Mikepattyn.Email) — .NET mail library
- [authress-sdk.rs](https://github.com/pattynologies/authress-sdk.rs) — Authress SDK for Rust

## How documentation works

Engineering pages live in the private Platform repository, under `docs/`. This page is the public map of that tree. It names folders and decision titles. It does not copy the pages.

Documentation is split into four kinds. A page belongs to one kind.

- **Tutorials** teach a path, from a starting point to a working result.
- **How-to guides** finish one task for someone who already knows the shape of the system.
- **Reference** states facts: names, versions, and settings.
- **Explanation** says why a choice was made.

Architecture decision records sit beside those four. They record a decision and its status. Research notes, API collections, security notes, and lesson source packs stay in their own folders.

## Folders

- `docs/tutorials` — learning path for running the workspace
- `docs/how-to` — task recipes for people who have the Platform repository
- `docs/reference` — toolchain, auth, and operator facts
- `docs/explanation` — why the Platform is shaped this way
- `docs/adr` — decision records; number, title, and status are listed below
- `docs/architecture` — diagram of the Platform
- `docs/bruno` — shop API requests
- `docs/bruno-authress` — shop Authress setup requests
- `docs/bruno-authress-umut-colak` — atelier Authress setup requests
- `docs/bruno-umut-colak` — atelier API requests
- `docs/migration` — notes left from earlier moves
- `docs/research` — source notes behind decisions
- `docs/security` — evaluations and response notes
- `docs/xai-collections` — lesson source packs for Learn

## How to add a page

People with access to the private Platform repository add a page there.

1. Put the new Markdown file in exactly one of `docs/tutorials`, `docs/how-to`, `docs/reference`, `docs/explanation`, or `docs/adr`.
2. Choose the folder by the job of the page: teach a path, finish a task, state a fact, or explain why.
3. Number a new decision record with the next free number. `0023` is unused. Take the next number after the highest number in the list below.
4. When a decision record is added, removed, or its status line changes, refresh the index from the Platform repository:

   ```bash
   node scripts/render-org-profile/render-org-profile.mjs
   ```

   Commit and push this repository (`pattynologies/.github`), then commit the submodule pin at `docs/org-profile` in the Platform repository.
5. When a top-level folder under `docs/` appears or disappears, edit the folder list above by hand, then push this repository and pin the submodule the same way.
6. Leave child titles out of this page for how-to guides, security notes, Bruno collections, research notes, and xAI collections.

## Decisions

<!-- adr-index:start -->
- 0001. Turbo, pnpm, and TypeScript CDK for this umbrella — Accepted (CDK language superseded by ADR 0002)
- 0002. C# .NET 10 CDK for platform infrastructure — Accepted
- 0003. One StackComposition per website — Accepted
- 0004. Per-environment BrandFrontend stacks — Accepted
- 0005. Rust Authress authorizer for Pattynologies admin — Accepted
- 0006. Authress AtelierAdmin for Umut Çolak — Accepted
- 0007. Shared BrandCdn hostname — Accepted
- 0008. Shared Angular 22 workspace, Learn stays public — Accepted for the shared workspace. The Learn location is ADR 0022. The Teach project decision is superseded by ADR 0012
- 0009. Guest Authress for verzoeken and beoordelingen — Accepted
- 0010. Echo on one t3.micro; Function URLs only for IAM machine callers — Accepted (EC2 + role-not-page). Function URL door superseded by ADR 0014
- 0011. Learn is not in this umbrella — Superseded by ADR 0019
- 0012. Teach is not in this umbrella — Accepted
- 0013. DashboardFrontendStack for operator feature flags — Accepted
- 0014. Echo IAM RestApi for Chat and retrieval — Accepted
- 0015. DeliveryStage on Order for the operator purchase desk — Accepted
- 0016. AlienButNice is a website on this umbrella — Accepted
- 0017. Echo dials a Learn-owned bot socket — Accepted
- 0018. alienbutnice.bot is its own website — Accepted
- 0019. Learn is a public gitlink on pattynologies.com — Superseded by ADR 0022
- 0020. Angular 22 inside the alienbutnice.nl gitlink — Accepted
- 0021. Meta match keys live on a TTL item, not the Order — Not recorded
- 0022. Learn is a project in the Angular workspace — Accepted
- 0024. Learn keeps the Cname host and gains a same-origin analytics API — Accepted
- 0025. Echo says hello once when a learner opens a classroom chat — Accepted
- 0026. Learn classroom chat lives in one NgRx store — Accepted
- 0027. Echo Chat Lambda is a Python Echo Brain — Accepted
- 0028. Angular 22 inside the thebees gitlink — Accepted
- 0029. Angular 22 inside the Lore gitlink — Accepted
- 0030. Angular 22 inside the Clover gitlink — Accepted
- 0031. The Fleet host: three identities — Accepted
- 0032. Angular 22 inside the Link gitlink — Accepted
- 0033. Angular 22 inside the Sage gitlink — Accepted
- 0034. Angular 22 inside the Nyxkin gitlink — Accepted
- 0035. Nyxkin hall names live in DynamoDB — Accepted
- 0036. Pattynologies code promotes by artifact version — Accepted
- 0037. The organization profile maps private documentation — Accepted
<!-- adr-index:end -->
