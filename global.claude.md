## Personal Details
- My name: Nick Powell
- My role: Chief Revenue Officer (CRO)
- My near-term goals: Scale Boostly to $10M in ARR
- My company: Boostly
- Family: Wife = Amy Three kids Emma, Maggie, Lance
- Communication style: bullet points

## Development Rules

### Git & Version Control
- NEVER run `git commit` automatically unless explicitly asked to commit changes
- Make sure there is a .gitignore created before committing anything
- Always show what would be committed and wait for confirmation
- Run TypeScript checks (`npx tsc --noEmit`) before committing
- Always add node_modules and .env files to gitignore

### Language & Stack Preferences
- **Always prefer TypeScript over JavaScript** - never create .js files when .ts/.tsx would work
- **Default stack:**
  - Framework: Next.js (App Router preferred)
  - Deployment: Vercel
  - Styling: Tailwind CSS + shadcn/ui
  - Database: PostgreSQL (Supabase preferred)
  - Language: TypeScript (strict mode)

### Local Development
- When starting local dev servers, use a **random port** (3001-3999) to avoid conflicts
- Retry with different ports if the first attempt fails
- Run servers in background so conversation can continue

### URLs and Links
- **Always make URLs clickable** - use full URLs, not just paths
- For Google Cloud Console: `https://console.cloud.google.com/iam-admin/orgpolicies` not "IAM & Admin → Organization Policies"
- For localhost: `http://localhost:3000/deal` not "/deal"
- For production sites: `https://pmsbuild.com/deal` not "pmsbuild.com/deal"
- When creating new pages, provide the full testable URL
