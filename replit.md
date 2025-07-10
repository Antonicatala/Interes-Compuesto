# Compound Interest Calculator

## Overview

This is a full-stack web application built with React (frontend) and Express.js (backend) that provides a compound interest calculator. The application is designed to help users understand the power of compound interest by calculating and visualizing investment growth over time. The interface is in Spanish and focuses on financial education.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack React Query for server state, React Hook Form for form management
- **UI Framework**: Shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ESM modules
- **Database ORM**: Drizzle ORM configured for PostgreSQL
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: Uses connect-pg-simple for PostgreSQL session storage

## Key Components

### Frontend Components
- **Calculator Form**: Main compound interest calculation interface with validation using Zod
- **UI Components**: Comprehensive set of reusable components from Shadcn/ui including cards, buttons, inputs, dialogs, and form controls
- **Responsive Design**: Mobile-first approach with responsive breakpoints

### Backend Components
- **Storage Interface**: Abstracted storage layer with in-memory implementation for development
- **Route Registration**: Centralized route management system
- **Middleware**: Request logging, JSON parsing, and error handling
- **Development Server**: Hot-reload capability with Vite integration

### Database Schema
- **Users Table**: Basic user management with username/password authentication
- **Validation**: Zod schemas for type-safe data validation
- **Migrations**: Drizzle migrations stored in `/migrations` directory

## Data Flow

1. **User Input**: Calculator form accepts initial amount, monthly contributions, annual interest rate, and time period
2. **Form Validation**: Client-side validation using Zod schemas and React Hook Form
3. **Calculation**: Frontend performs compound interest calculations locally
4. **Results Display**: Visual presentation of investment growth comparison (with vs without compound interest)
5. **API Integration**: Backend ready for user management and calculation history storage

## External Dependencies

### Frontend Dependencies
- **UI/UX**: Radix UI primitives, Lucide React icons, Tailwind CSS
- **Form Management**: React Hook Form with Zod resolvers
- **Data Fetching**: TanStack React Query
- **Date Handling**: date-fns library
- **Carousel**: Embla Carousel for component interactions

### Backend Dependencies
- **Database**: Neon Database (serverless PostgreSQL), Drizzle ORM
- **Development**: tsx for TypeScript execution, esbuild for production builds
- **Session Management**: express-session with PostgreSQL store

### Development Tools
- **Build System**: Vite with React plugin and runtime error overlay
- **Type Safety**: TypeScript with strict configuration
- **Code Quality**: ESLint configuration through Vite
- **Replit Integration**: Cartographer plugin for development environment

## Deployment Strategy

### Development
- **Local Development**: `npm run dev` starts development server with hot reload
- **Database**: `npm run db:push` for schema synchronization
- **Type Checking**: `npm run check` for TypeScript validation

### Production
- **Build Process**: `npm run build` creates optimized frontend bundle and backend server
- **Output**: Frontend assets to `dist/public`, backend bundle to `dist/index.js`
- **Runtime**: `npm start` runs production server with NODE_ENV=production

### Environment Configuration
- **Database URL**: Required environment variable for PostgreSQL connection
- **Session Management**: PostgreSQL-backed sessions for scalability
- **Static Assets**: Express serves built frontend assets in production

### Architecture Decisions

**Problem**: Need for type-safe database operations and schema management
**Solution**: Drizzle ORM with PostgreSQL and Zod validation
**Benefits**: Type safety, auto-generated types, easy migrations
**Trade-offs**: Learning curve for Drizzle syntax vs traditional ORMs

**Problem**: Complex UI component requirements
**Solution**: Shadcn/ui component library built on Radix UI
**Benefits**: Accessible, customizable, TypeScript-ready components
**Trade-offs**: Larger bundle size vs custom components

**Problem**: Development and production environment consistency
**Solution**: Vite for development with Express serving static files in production
**Benefits**: Fast hot reload in development, single deployment artifact
**Trade-offs**: Complexity in build configuration vs separate frontend/backend deployments

The application is structured as a monorepo with shared TypeScript schemas and clear separation between client and server code, making it maintainable and scalable for financial calculation features.