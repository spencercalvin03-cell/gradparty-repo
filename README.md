# GradParty

A web app for high school seniors to discover, schedule, and RSVP to graduation parties.

## Features (MVP)

- **Join school** — Onboarding flow: create a profile and select your school
- **View events** — Browse all parties at your school, filterable and searchable
- **Calendar** — Visual monthly calendar with heat indicators for busy days
- **Create event** — Host a party with title, date, time, description, location, and privacy settings
- **RSVP** — Mark yourself as Going / Maybe / Can't go on any event
- **Event detail** — Full detail view with host info, location reveal, and RSVP counts
- **Profile** — View your hosted events and events you're attending

All state is stored in `localStorage` — no backend required.

---

## File structure

```
gradparty/
├── public/
│   └── index.html              # HTML shell
├── src/
│   ├── context/
│   │   ├── AppContext.js       # Global state, reducer, localStorage persistence
│   │   └── useToast.js         # Toast notification hook
│   ├── components/
│   │   ├── Navbar.js           # Top navigation bar
│   │   ├── Onboarding.js       # 3-step join school flow
│   │   ├── EventsList.js       # Events list with filters + search
│   │   ├── EventDetail.js      # Single event detail page
│   │   ├── CreateEvent.js      # Create party form
│   │   ├── Calendar.js         # Monthly calendar grid
│   │   ├── Profile.js          # User profile page
│   │   └── EventCard.js        # Reusable event card component
│   ├── App.js                  # Root component + routing
│   ├── index.js                # React entry point
│   └── index.css               # All styles (CSS variables + utility classes)
├── package.json
├── vercel.json
└── README.md
```

---

## Running locally

### Prerequisites

- Node.js 18+ — https://nodejs.org
- npm (comes with Node)

### Steps

```bash
# 1. Clone or download the project
cd gradparty

# 2. Install dependencies
npm install

# 3. Start the development server
npm start
```

The app will open at **http://localhost:3000**.

---

## Building for production

```bash
npm run build
```

This creates an optimized production build in the `build/` folder.

---

## Deploying to Vercel

### Option A — Vercel CLI

```bash
# Install the Vercel CLI globally
npm install -g vercel

# Deploy from the project root
vercel
```

Follow the prompts. Vercel will auto-detect Create React App and configure everything.

### Option B — Vercel Dashboard (recommended)

1. Push the project to a GitHub repository
2. Go to https://vercel.com and click **Add New Project**
3. Import your GitHub repository
4. Vercel auto-detects the framework — no config needed
5. Click **Deploy**

Your app will be live at a `.vercel.app` URL within ~60 seconds.

The `vercel.json` in this project is pre-configured:

```json
{
  "buildCommand": "npm run build",
  "outputDirectory": "build",
  "framework": "create-react-app"
}
```

---

## Environment variables

None required. The app uses `localStorage` for all data persistence and needs no backend or API keys.

---

## Tech stack

| Layer      | Technology                              |
|------------|-----------------------------------------|
| Framework  | React 18                                |
| Routing    | React Router v6                         |
| State      | useReducer + Context API + localStorage |
| Styling    | Plain CSS (no framework)                |
| Fonts      | Google Fonts (Syne + DM Sans)           |
| Build tool | Create React App                        |
| Deploy     | Vercel                                  |

---

## Next steps (post-MVP)

- Add a real backend (e.g. Supabase or Firebase) for shared data across users
- School email verification via magic link
- Push notifications for new events
- Friend system and friend activity feed
- Map view of events
