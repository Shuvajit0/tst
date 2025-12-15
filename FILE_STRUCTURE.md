# 📋 File Structure & Component Reference

## Project Root Files

```
scriptforge/
├── .env.example                    # Environment variables template
├── .github/                        # GitHub files
│   └── PROGRESS.md                # Implementation progress tracker
├── .gitignore                      # Git ignore rules
├── .next/                          # Next.js build output
├── eslint.config.mjs               # ESLint configuration
├── next.config.js                  # Next.js configuration
├── next-env.d.ts                   # Next.js TypeScript definitions
├── node_modules/                   # Dependencies (npm install)
├── package.json                    # Project dependencies & scripts
├── package-lock.json               # Dependency lock file
├── postcss.config.mjs              # PostCSS configuration
├── tailwind.config.ts              # Tailwind CSS configuration
├── tsconfig.json                   # TypeScript configuration
├── README.md                       # Full documentation
├── QUICK_START.md                  # Quick start guide
└── IMPLEMENTATION_SUMMARY.md       # Detailed feature summary
```

---

## Source Code Structure

### `src/app/` - Pages & Routes

#### Public Pages (No Auth Required)
- **`page.tsx`** - Landing page
  - Hero section with gradient text
  - How it works (3 steps)
  - 6 key features
  - Target audience section
  - 3 pricing tiers
  - FAQ with common questions
  - Final CTA section

- **`api/generateScript/route.ts`** - AI API endpoint
  - POST handler for script generation
  - Validates input
  - Calls AI prompt builder
  - Parses response
  - Returns structured output

#### Auth Pages
- **`auth/register/page.tsx`** - Sign up page
  - Form with email, name, password, confirm password
  - Form validation
  - Error display
  - Google OAuth button (ready)
  - Link to login

- **`auth/login/page.tsx`** - Sign in page
  - Email and password inputs
  - Remember me checkbox
  - Forgot password link
  - Google OAuth button (ready)
  - Link to register

- **`auth/forgot-password/page.tsx`** - Password reset (placeholder)

#### App Pages (Auth Required)
- **`dashboard/page.tsx`** - Main dashboard
  - User welcome message
  - 3 stat cards (plan, scripts, limits)
  - Create new script button
  - List of recent scripts
  - Upgrade prompt for free users

- **`scripts/new/page.tsx`** - Script creation page
  - Form on left (sticky)
  - Script viewer on right
  - Real-time generation
  - Loading state handling
  - Error handling

- **`billing/page.tsx`** - Pricing & billing page
  - All 3 pricing plans displayed
  - Feature comparison
  - Upgrade buttons
  - Billing FAQ
  - Support contact section

#### Layout & Styling
- **`layout.tsx`** - Root layout component
  - Global providers setup
  - Metadata configuration
  - Body styling

- **`globals.css`** - Global styles
  - Tailwind directives
  - Custom scrollbar styling
  - Selection colors
  - Animation definitions

---

### `src/components/` - Reusable Components

#### UI Components (`ui/`)
All basic UI components with Tailwind styling:

- **`Button.tsx`**
  - Variants: primary, secondary, outline, ghost
  - Sizes: sm, md, lg
  - Loading state
  - Props: className, disabled, isLoading, etc.

- **`Input.tsx`**
  - Label optional
  - Error message display
  - Tailwind styling
  - Dark mode support

- **`Select.tsx`**
  - Dropdown select component
  - Label and error support
  - Options array prop
  - Dark mode support

- **`Textarea.tsx`**
  - Multi-line text input
  - Label and error support
  - Resizable
  - Dark mode support

- **`Card.tsx`**
  - Container component
  - Consistent rounded/shadow styling
  - Dark mode background
  - Border styling

- **`index.ts`** - Exports all UI components

#### Layout Components (`layout/`)

- **`Navigation.tsx`**
  - Responsive navigation bar
  - Logo and branding
  - Menu links (public/auth)
  - Dark mode toggle with Lucide icons
  - Mobile hamburger menu
  - Auth buttons (login, register, logout)
  - Sticky positioning

- **`Footer.tsx`**
  - Company info
  - Links (Product, Company, Legal)
  - Social links
  - Copyright info
  - Dark mode support

- **`index.ts`** - Exports layout components

#### Feature Components (`features/`)

- **`ScriptForm.tsx`**
  - Complete form for script generation
  - React Hook Form integration
  - All 6 input fields:
    - Topic (required, min 3 chars)
    - Video length select
    - Content type select
    - Language select
    - Tone select
    - Additional notes textarea
  - Submit button with loading state
  - Error display
  - Form validation

- **`ScriptViewer.tsx`**
  - Display generated scripts
  - Sections:
    - Title options (numbered list)
    - Hook (main text)
    - Main script (with formatting)
    - Ending & CTA
    - Visual suggestions (bulleted)
  - Action buttons:
    - Copy to clipboard (with feedback)
    - Download as .txt
    - Save to account (ready)
  - Icon integration with Lucide

- **`index.ts`** - Exports feature components

---

### `src/lib/` - Business Logic

#### Core Configuration (`config.ts`)
- Supabase URL and keys
- AI API configuration
- Plan limits (free/starter/pro)
- Content types array
- Tones array
- Languages array
- Video length descriptions
- Branding configuration (name, logo, colors, tagline)

#### AI Integration (`ai/`)

- **`prompt-builder.ts`**
  - `buildScriptPrompt(input)` - Creates detailed AI prompt
  - `parseScriptResponse(response)` - Extracts sections from AI response
  - Language name mapping
  - Prompt structure with clear section headers

- **`openai-client.ts`**
  - `generateScriptWithAI(options)` - Calls OpenAI API
  - `generateScriptWithAIMock(options)` - Mock for development
  - Error handling
  - Token limit configuration
  - Temperature and parameters

#### Database (`db/`)

- **`supabase.ts`**
  - Supabase client initialization
  - Environment variable validation
  - Type definitions

---

### `src/store/` - Global State (Zustand)

- **`auth-store.ts`**
  - User state management
  - Auth actions: setUser, setLoading, setError, logout
  - Global auth state

- **`script-store.ts`**
  - Scripts list state
  - Current script state
  - Script actions: setScripts, addScript, deleteScript, setCurrentScript
  - Generation state: setGenerating, setError

---

### `src/hooks/` - Custom React Hooks

- **`useTheme.ts`**
  - Dark/light mode management
  - localStorage persistence
  - System preference detection
  - Theme toggle function
  - Mounted state for hydration

---

### `src/types/` - TypeScript Definitions

- **`index.ts`**
  - `VideoLength` - 'short' | 'long'
  - `ContentType` - 'tutorial' | 'storytelling' | 'review' | 'vlog'
  - `Tone` - 'funny' | 'serious' | 'professional' | 'storytelling' | 'motivational'
  - `Language` - 'english' | 'spanish' | 'french' | 'german' | 'portuguese'
  - `PlanType` - 'free' | 'starter' | 'pro'
  - `User` - User profile interface
  - `ScriptGenerationInput` - Form input interface
  - `GeneratedScript` - Complete script object
  - `ScriptSection` - Script section with timestamp
  - `PlanDetails` - Pricing plan interface
  - `SubscriptionData` - Subscription status interface

---

## Key Algorithms & Logic

### Script Generation Flow
1. User fills ScriptForm → calls handleGenerateScript
2. Form validated with React Hook Form
3. POST to `/api/generateScript` with form data
4. API builds prompt using `buildScriptPrompt()`
5. AI generates response (real or mock)
6. Response parsed with `parseScriptResponse()`
7. ScriptViewer displays formatted output
8. User can copy, download, or save

### State Management Flow
1. Global stores (Zustand) maintain auth and script state
2. Components read from stores with hooks
3. Actions update stores on user interaction
4. Components re-render on store changes
5. localStorage syncs auth state (mock)

### Theme System
1. useTheme hook checks localStorage
2. Falls back to system preference
3. Applies dark class to HTML element
4. Tailwind dark: prefix handles styles
5. Theme persists across sessions

---

## Environment Variables

### Required
```
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
AI_API_KEY=your_openai_api_key
```

### Optional
```
AI_API_PROVIDER=openai
AI_MODEL=gpt-4
NEXT_PUBLIC_API_URL=http://localhost:3000
```

---

## Styling Architecture

### Tailwind Configuration
- Content glob patterns for scans
- Dark mode: 'class' based
- Extended colors: primary (#EC4899), accent (#A855F7)
- Font family variables from Google Fonts

### CSS Organization
1. **globals.css** - Global styles and resets
2. **Tailwind directives** - @tailwind base/components/utilities
3. **Component classes** - Utility classes in components
4. **Dark mode** - Using dark: prefix
5. **Responsive** - Using sm:, md:, lg: prefixes

### Color Palette
- Primary: Pink #EC4899
- Accent: Purple #A855F7
- Backgrounds: White/Gray-950
- Text: Gray-900/White
- Borders: Gray-200/Gray-800

---

## Component Dependencies

### Navigation dependencies:
- next/link
- next/navigation (usePathname)
- clsx (conditional classes)
- Lucide icons (Menu, X, Moon, Sun)
- Button UI component
- useTheme hook

### ScriptForm dependencies:
- react-hook-form
- Button, Input, Select, Textarea UI
- Types (ScriptGenerationInput, etc.)
- Config (CONTENT_TYPES, TONES, etc.)

### ScriptViewer dependencies:
- Lucide icons (Copy, Download)
- Button UI component
- Card UI component
- Types (GeneratedScript)

---

## Build Information

### TypeScript Build
- Target: ES2017
- Module: esnext
- Strict mode enabled
- Path aliases: @/* → src/*
- Type checking on build

### Production Build Output
- Route status: Static (○) or Dynamic (ƒ)
- All pages compile without errors
- Optimized bundle sizes
- Ready for deployment

---

## Testing & Verification

### Manual Testing Checklist
- [ ] Landing page loads with all sections
- [ ] Dark mode toggle works
- [ ] Form validation shows errors
- [ ] Script generation shows loading state
- [ ] Copy button copies text
- [ ] Download creates .txt file
- [ ] Navigation links work
- [ ] Responsive on mobile (375px+)
- [ ] Responsive on tablet (768px+)
- [ ] Responsive on desktop (1024px+)

### Build Verification
- [ ] npm run build completes with 0 errors
- [ ] No TypeScript errors
- [ ] No ESLint warnings (can ignore)
- [ ] All routes compile successfully

---

## File Sizes & Performance

- Main app JS bundle: ~100-150KB (with dependencies)
- CSS: ~30-50KB (Tailwind purged)
- Pages: 5-15KB each
- Total load time: <2 seconds on localhost

---

## Deployment Checklist

- [ ] Configure Supabase database
- [ ] Set environment variables
- [ ] Connect OpenAI API
- [ ] Test script generation
- [ ] Configure domain/DNS
- [ ] Set up HTTPS/SSL
- [ ] Configure CDN (optional)
- [ ] Set up monitoring
- [ ] Configure backups
- [ ] Deploy to Vercel or hosting platform

---

## Support Files

- **README.md** - Full documentation (3,598 bytes)
- **QUICK_START.md** - Quick start guide
- **IMPLEMENTATION_SUMMARY.md** - Detailed features summary (13,647 bytes)
- **PROGRESS.md** - Implementation checklist
- **.env.example** - Environment template (359 bytes)

---

**That's the complete project structure! Ready to build amazing YouTube scripts.** 🚀
