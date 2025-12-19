# MemberJunction Template

A production-ready monorepo template for building applications with [MemberJunction](https://www.memberjunction.org/).

## Automated Provisioning

When you create an environment through **MJ Central**, provisioning happens automatically:

### What Gets Provisioned

- **GitHub Repository**
- **Git Branches** - One per environment (dev, stage, prod, or custom names)
- **Azure Resources** - App Service, Static Web App, SQL Database
- **GitHub Secrets & Variables** - Configured per environment
- **Workflows** - Triggered automatically to deploy your environment

### Workflow Execution Order

1. **mj-setup** - Initializes database schema and generates code
2. **explorer** - Deploys the Angular admin UI (runs after mj-setup succeeds)
3. **api** - Deploys the GraphQL API server (runs after mj-setup succeeds)

### After Provisioning

**If all workflows succeed:**
- Environment status shows **Running** in MJ Central
- You'll receive a confirmation email
- Your apps are live and accessible

**If any workflow fails:**
1. Go to **GitHub Actions** in your repository
2. Check the failed workflow logs for details
3. Try clicking **Re-run jobs** to retry
4. Still failing? Contact **help@memberjunction.com**

## What's Included

- **MJ API** (`apps/MJAPI`) - GraphQL API server
- **MJ Explorer** (`apps/MJExplorer`) - Angular admin UI
- **Generated Entities** (`packages/GeneratedEntities`) - Auto-generated TypeScript entities
- **Generated Actions** (`packages/GeneratedActions`) - Auto-generated business logic
- **SQL Migrations** (`SQL Scripts/migrations/`) - Database migration structure

## Local Development

See the [Local Development Guide](docs/LOCAL_DEVELOPMENT.md) for running this project locally.

## Support

- **Issues:** help@memberjunction.com
- **Documentation:** [docs.memberjunction.org](https://docs.memberjunction.org/)
