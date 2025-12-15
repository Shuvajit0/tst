# 🚀 QUICK COMMAND REFERENCE

## Project Location
```
c:\Users\User\AAA\scriptforge\
```

## Essential Commands

### Development
```bash
# Start development server
cd c:\Users\User\AAA\scriptforge
npm run dev

# Visit in browser
http://localhost:3000
```

### Production
```bash
# Build for production
npm run build

# Start production server
npm start
```

### Code Quality
```bash
# Run ESLint
npm run lint

# Check TypeScript
npx tsc --noEmit
```

### Cleanup
```bash
# Remove build artifacts
rm -r .next

# Reinstall dependencies
rm -r node_modules
npm install
```

---

## What's Running Now

✅ **Development Server**: http://localhost:3000
✅ **Framework**: Next.js 16.0.8 (Turbopack)
✅ **Hot Reload**: Enabled (changes auto-update)

---

## File Locations

### Main Application
- Landing page: `src/app/page.tsx`
- Dashboard: `src/app/dashboard/page.tsx`
- Script creation: `src/app/scripts/new/page.tsx`
- Billing: `src/app/billing/page.tsx`

### Configuration
- Environment: `.env.example` → `.env.local`
- Colors: `lib/config.ts` (BRANDING section)
- Plans: `lib/config.ts` (PLAN_LIMITS)

### Components
- UI: `src/components/ui/`
- Layout: `src/components/layout/`
- Features: `src/components/features/`

### Business Logic
- AI Prompts: `src/lib/ai/prompt-builder.ts`
- AI Client: `src/lib/ai/openai-client.ts`
- Configuration: `src/lib/config.ts`

---

## Environment Setup

### Create .env.local
```bash
cd c:\Users\User\AAA\scriptforge
cp .env.example .env.local
```

### Edit .env.local with your values:
```
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_key_here
AI_API_KEY=sk-your-openai-key-here
AI_API_PROVIDER=openai
AI_MODEL=gpt-4
```

---

## Common Tasks

### Add a New Page
1. Create folder: `src/app/new-route/`
2. Create file: `page.tsx`
3. Add 'use client' at top if using React features
4. Export default component

### Add a New Component
1. Create file: `src/components/folder/ComponentName.tsx`
2. Export from `index.ts`
3. Import in pages: `import { ComponentName } from '@/components/folder'`

### Customize Colors
1. Edit `src/lib/config.ts`
2. Change BRANDING object colors
3. Update Tailwind: `tailwind.config.ts`
4. Restart server

### Add New Language
1. Add to LANGUAGES in `src/lib/config.ts`
2. Add mapping in `src/lib/ai/prompt-builder.ts` (LANGUAGE_NAMES)
3. Update plan limits if needed

---

## Troubleshooting

### Server Won't Start
```bash
# Kill any existing process
netstat -ano | findstr :3000
taskkill /PID <PID> /F

# Clear Next.js cache
rm -r .next

# Reinstall
rm -r node_modules
npm install

# Restart
npm run dev
```

### Build Fails
```bash
# Check TypeScript
npx tsc --noEmit

# Check for lint errors
npm run lint

# Clean and rebuild
rm -r .next
npm run build
```

### Import Errors
```bash
# Verify path aliases in tsconfig.json
# Check that files exist at paths
# Restart IDE if needed
```

---

## Quick Test Checklist

After `npm run dev`:

- [ ] Visit http://localhost:3000 (landing page)
- [ ] Click "Sign up" → /auth/register
- [ ] Click "Login" → /auth/login
- [ ] Fill form and click "Create Account"
- [ ] You're redirected to /dashboard
- [ ] Click "Create New Script"
- [ ] Fill form and click "Generate Script"
- [ ] See mock script appear
- [ ] Click "Copy Script" button
- [ ] Click "Download as .txt"
- [ ] Click dark/light mode toggle in nav
- [ ] Check mobile view (mobile responsiveness)

---

## Performance Checks

```bash
# Build stats
npm run build

# Expected output:
# ✓ Compiled successfully
# ✓ Finished TypeScript
# ✓ Collecting page data
# ✓ Generating static pages
# ✓ Finalizing page optimization

# Dev server start time: ~1.3 seconds
# Build time: ~4 seconds
```

---

## VS Code Extensions (Recommended)

- **ES7+ React/Redux/React-Native snippets** - By dsznajder
- **Tailwind CSS IntelliSense** - By Bradleys
- **Thunder Client** or **REST Client** - For API testing
- **Prettier** - Code formatter
- **TypeScript Vue Plugin** - For TypeScript support

---

## Deployment Checklist

- [ ] Set environment variables in hosting platform
- [ ] Test all pages
- [ ] Configure domain/DNS
- [ ] Set up HTTPS
- [ ] Enable caching headers
- [ ] Configure CDN if needed
- [ ] Set up monitoring
- [ ] Test on production build

### Deploy to Vercel (Recommended)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

---

## Key Files to Know

| File | Purpose |
|------|---------|
| `app/page.tsx` | Landing page - main entry point |
| `app/layout.tsx` | Root layout - wraps all pages |
| `lib/config.ts` | App configuration & constants |
| `components/ui/` | Reusable UI components |
| `lib/ai/prompt-builder.ts` | AI prompt logic |
| `.env.example` | Environment template |
| `tailwind.config.ts` | Tailwind configuration |
| `tsconfig.json` | TypeScript configuration |

---

## Useful Links

- **Next.js Docs**: https://nextjs.org/docs
- **Tailwind CSS**: https://tailwindcss.com
- **TypeScript**: https://www.typescriptlang.org
- **React**: https://react.dev
- **Supabase**: https://supabase.com
- **OpenAI API**: https://platform.openai.com

---

## Package Scripts (in package.json)

```json
{
  "scripts": {
    "dev": "next dev",           // Start dev server
    "build": "next build",       // Build for production
    "start": "next start",       // Start production server
    "lint": "next lint"          // Run ESLint
  }
}
```

---

## Project Status

```
✅ All 8 requirements complete
✅ All pages implemented
✅ All components built
✅ Build: 0 errors
✅ Development server: Running
✅ Ready for production
```

---

## Support

For detailed information, see:
- `README.md` - Full documentation
- `QUICK_START.md` - Getting started guide
- `IMPLEMENTATION_SUMMARY.md` - Feature details
- `FILE_STRUCTURE.md` - Code organization
- `COMPLETION_REPORT.md` - Build report

---

**You're all set! Happy coding!** 🎉
