# Instant Moodboard Generator

## Overview

This is a React-based web application that generates comprehensive design moodboards from user input. Users can enter a vibe or theme description (e.g., "dreamy underwater city", "cozy autumnal cabin") and the application creates a visual moodboard containing color palettes, typography suggestions, keywords, and relevant images. The app is designed to serve as a quick source of visual inspiration for designers and creatives.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **UI Library**: Shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack React Query for server state management
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ESM modules
- **API Design**: RESTful API endpoints with JSON responses
- **Data Storage**: In-memory storage using Map data structure (MemStorage class)
- **Schema Validation**: Zod schemas for type-safe data validation
- **Database ORM**: Drizzle ORM configured for PostgreSQL (schema defined but using memory storage)

### Core Services
- **AI Integration**: OpenAI GPT-5 for keyword generation and random vibe creation
- **Image Service**: Unsplash API for fetching high-quality images based on keywords
- **Color Generation**: Custom algorithm that maps keywords to color palettes
- **Typography**: Google Fonts integration for font suggestions

### Key Features
- **Moodboard Generation**: Transforms text input into visual elements (keywords, colors, images, fonts)
- **Sharing System**: Generates shareable URLs for moodboards
- **Export Functionality**: Save moodboards as PNG images
- **Interactive Tools**: Shuffle button for regenerating with same theme, random vibe generator
- **Responsive Design**: Mobile-first design with Tailwind CSS

### Data Flow
1. User inputs vibe description through React form
2. Frontend sends POST request to `/api/moodboards/generate`
3. Backend processes input through OpenAI service to extract keywords
4. Color palette generated from keywords using custom algorithm
5. Images fetched from Unsplash API based on keyword combinations
6. Typography suggestions generated based on vibe characteristics
7. Complete moodboard data stored in memory and returned to frontend
8. React Query manages caching and state updates

## External Dependencies

### APIs and Services
- **OpenAI API**: GPT-5 model for natural language processing and keyword extraction
- **Unsplash API**: High-quality stock photography for moodboard images
- **Google Fonts**: Typography suggestions and font loading

### Database
- **PostgreSQL**: Configured via Drizzle ORM (DATABASE_URL environment variable)
- **Neon Database**: Serverless PostgreSQL provider (@neondatabase/serverless)

### Development Tools
- **Replit Integration**: Vite plugins for development banner and cartographer
- **TypeScript**: Full type safety across frontend and backend
- **ESBuild**: Production bundling for server code

### UI/UX Libraries
- **Radix UI**: Comprehensive primitive components for accessibility
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide React**: Icon library for consistent iconography
- **Embla Carousel**: Touch-friendly carousel components

The application follows a clean separation of concerns with shared types between frontend and backend, comprehensive error handling, and a modular service architecture that makes it easy to extend functionality.