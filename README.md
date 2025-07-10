# Lore Web Interface

**Modern web interface for the Lore research system with interactive knowledge graph visualization.**

## Overview

Lore Web provides a beautiful, fast web interface for exploring research data from the Lore engine. Built with TanStack libraries for optimal performance and developer experience.

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Connect to Lore engine
# Set LORE_API_URL=http://localhost:3000 in .env
```

## 🎯 Features

- **Interactive Knowledge Graph** - D3.js force-directed visualization
- **Real-time Research Monitoring** - Live updates via Server-Sent Events
- **Advanced Search & Filtering** - Full-text search with faceted filtering
- **Virtualized Performance** - Handle thousands of notes smoothly
- **Responsive Design** - Works on desktop, tablet, and mobile
- **Dark Mode** - Clean, readable interface inspired by TanStack

## 🛠️ Technology Stack

- **React 18** - Modern React with Suspense and Concurrent Features
- **TanStack Router** - Type-safe file-based routing
- **TanStack Query** - Data fetching and caching
- **TanStack Table** - Performant data tables
- **TanStack Virtual** - Virtualized lists and grids
- **D3.js** - Knowledge graph visualization
- **Tailwind CSS** - Utility-first styling
- **TypeScript** - End-to-end type safety

## 🔌 Lore API Integration

**API Version**: `1.0.0`  
**Types**: Imports from `@lore/api-types` (references lore engine `src/interfaces/api.ts`)  
**Specification**: Follows `lore/docs/api/openapi.yaml`

```typescript
import { LoreNote, LoreResearchSession } from '@lore/api-types';

// Type-safe API client
const session = await loreApi.research.start({
  topic: "sustainable packaging",
  depth_limit: 2
});
```

## 📁 Project Structure

```
lore-web/
├── src/
│   ├── components/           # Reusable UI components
│   │   ├── notes/           # Note-related components
│   │   ├── graph/           # Knowledge graph components
│   │   ├── search/          # Search and filtering
│   │   └── ui/              # Base UI components
│   ├── pages/               # Route components
│   │   ├── dashboard/       # Research dashboard
│   │   ├── notes/           # Note explorer
│   │   ├── graph/           # Graph visualization
│   │   └── search/          # Search interface
│   ├── lib/                 # Utilities and API client
│   │   ├── api/             # Lore API client
│   │   ├── graph/           # Graph algorithms
│   │   └── utils/           # Helper functions
│   ├── hooks/               # React hooks
│   └── styles/              # Global styles and themes
├── public/                  # Static assets
└── docs/                    # Component documentation
```

## 🎨 Design System

Inspired by TanStack's clean, developer-focused aesthetic:

- **Typography**: Clear hierarchy with excellent readability
- **Colors**: Dark theme with cyan accents (#00d9ff)
- **Layout**: Dense, information-rich layouts
- **Animation**: Minimal, purposeful animations
- **Performance**: 60fps interactions, efficient rendering

## 📊 Core Components

### Knowledge Graph (`/graph`)
- Force-directed D3.js visualization
- Interactive zoom and pan
- Node filtering by type, confidence, tags
- Edge highlighting for relationships
- Minimap for navigation

### Research Dashboard (`/dashboard`)
- Real-time progress monitoring
- Active agent display
- Source preview cards
- Session controls (pause/resume)

### Note Explorer (`/notes`)
- Virtualized note list (handles 10k+ notes)
- Advanced filtering and search
- Tag cloud visualization  
- Confidence indicators
- Export options

### Search Interface (`/search`)
- Full-text search with highlighting
- Faceted filtering (tags, types, sources)
- Search history and saved queries
- Semantic search (when available)

## 🔄 Real-time Updates

Uses Server-Sent Events for live research updates:

```typescript
// Real-time research progress
useResearchEvents(sessionId, {
  onProgress: (data) => updateProgress(data),
  onNoteCreated: (note) => addNoteToGraph(note),
  onCompletion: () => showNotification("Research complete!")
});
```

## 🧪 Development

```bash
# Development with hot reload
npm run dev

# Type checking
npm run typecheck

# Linting
npm run lint

# Testing
npm run test

# Storybook (component docs)
npm run storybook
```

## 🚀 Deployment

```bash
# Build static site
npm run build

# Preview production build
npm run preview

# Deploy to Vercel/Netlify
npm run deploy
```

The built site is a static SPA that connects to any Lore engine instance via the REST API.

## 🔧 Configuration

```env
# .env
LORE_API_URL=http://localhost:3000
LORE_API_KEY=optional_api_key
VITE_APP_TITLE=Lore Research
VITE_GRAPH_MAX_NODES=1000
```

## 🤝 Contributing

1. Reference Lore API specification for integration changes
2. Follow TanStack component patterns
3. Maintain performance with large datasets
4. Test with real research data
5. Document new visualization features

## 📄 License

MIT License - see LICENSE file for details.

---

**Note**: This is a standalone web interface that connects to the Lore research engine. See the main [lore repository](https://github.com/chreez/lore) for the core research system.