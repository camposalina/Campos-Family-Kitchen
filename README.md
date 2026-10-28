# Campos-Family-Kitchen --- Engineering Documentation
Version: 1.0
Scope: Shared grocery inventory and shopping runs
Status: Starting specification
Product goal
Build a responsive web app for one household. Household members can
maintain a shared grocery inventory, create shopping runs, mark items as
placed in the cart, edit the list during shopping, confirm the actual
purchase after checkout, and replenish home inventory from confirmed
purchases.
MVP boundaries
In scope
- Authentication and household membership for two adults.
- Product catalog with product name, category, default unit, and
  optional notes.
- Home inventory with quantities and storage locations.
- CRUD for products and inventory entries.
- Shopping runs with editable items.
- Cart status distinct from purchase status.
- Checkout review and explicit purchase confirmation.
- Replenish inventory from confirmed purchases.
- Responsive UI, server-side validation, authorization, basic
  automated tests.
Out of scope
- Meal planning and recipes.
- School snacks and baby-food workflows.
- AI, barcode scanning, receipt scanning, retailer integrations.
- Nutrition tracking.
- Complex invitation management for many households.
Core workflow
1. Create products and inventory entries manually.
2. Start a shopping run and add products or quick custom items.
3. Check items as they are put in the cart. This does not change
   inventory.
4. At checkout, review each item and correct the actual purchased
   quantity or mark it not purchased.
5. Confirm the run. The run becomes immutable for purchase confirmation
   purposes.
6. Click Replenish inventory. Confirmed purchased quantities are
   added to inventory.
7. The app records that replenishment was applied, preventing
   accidental duplicate additions.
Recommended stack
- Next.js App Router + React + TypeScript (strict: true)
- Supabase Auth + PostgreSQL
- Tailwind CSS
- Zod for input validation
- Vitest + React Testing Library
- Playwright for high-value end-to-end tests
- GitHub for version control; Vercel for deployment
Start with current stable compatible versions and follow official
documentation. Do not add an LLM API or other external integrations to
the MVP.
Suggested milestones
1. Project shell, navigation, sample UI.
2. Supabase connection and authentication.
3. Household membership and RLS.
4. Products and inventory CRUD.
5. Shopping run creation and editable items.
6. Checkout confirmation.
7. Idempotent inventory replenishment.
8. Tests, responsive polish, deployment.
Documentation index
- 01-product-requirements.md --- user stories and acceptance
  criteria.
- 02-architecture.md --- application structure and security
  boundaries.
- 03-data-model.md --- tables, fields, relationships, constraints.
- 04-business-rules.md --- cart, checkout, replenishment rules.
- 05-ui-flows.md --- screens and states.
- 06-implementation-plan.md --- coding milestones and definition of
  done.
- 07-testing-plan.md --- unit, integration, security, and end-to-end
  tests.
- 08-cursor-prompts.md --- prompts for incremental AI-assisted work.
- 09-decisions-and-risks.md --- initial architectural decisions and
  open questions.
Product success criteria
The MVP is usable when two household members can sign in from separate
devices, see the same inventory and shopping run, edit items without
losing data, confirm actual purchases, and replenish inventory exactly
once.
