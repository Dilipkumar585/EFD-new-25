# EFD Multi-User Service Platform

## Overview

This is a comprehensive multi-user service delivery platform (EFD - Emergency Fuel Delivery) built with React, Express, TypeScript, and PostgreSQL. The platform supports 4 user types with role-based authentication and dashboards:

1. **Customers** - Request fuel, ambulance, or mechanic services
2. **Petrol Bunk Workers** - Accept and fulfill fuel delivery requests  
3. **Ambulance Drivers** - Respond to emergency requests
4. **Mechanics** - Handle vehicle repair requests

Key features include splash screen branding, role-based authentication, live location tracking, real-time request assignment, and QR code payment generation.

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Changes (August 2025)

- **Complete authentication system overhaul** - Added multi-role user authentication with JWT tokens
- **Database migration** - Moved from in-memory to PostgreSQL with user roles, sessions, and enhanced request tracking  
- **Splash screen and login UI** - Added branded EFD splash screen and role-based login interface
- **Role-based dashboards** - Separate interfaces for customers vs. service providers
- **Sample user creation** - Automated sample user generation with credentials (user1/petrol1/ambulance1/mechanic1, all with password "password123")

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript and Vite as the build tool
- **UI Framework**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom design tokens and CSS variables
- **Routing**: wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **Form Handling**: React Hook Form with Zod validation resolvers

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Design**: RESTful API with structured error handling and request logging
- **Development**: Hot reload with Vite integration in development mode
- **Build Process**: esbuild for server bundling, separate from client build

### Data Storage
- **Database**: PostgreSQL configured through Drizzle ORM
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Development Storage**: In-memory storage implementation for rapid prototyping
- **Connection**: Neon Database serverless PostgreSQL adapter

### Database Schema Design
- **Users**: Basic user management with balance tracking for payments
- **Service Providers**: Provider profiles with real-time location and status tracking
- **Service Requests**: Central entity linking users and providers with detailed service information
- **Payments**: Transaction history with debit/credit tracking

### Authentication & Security
- Session-based authentication using PostgreSQL session store
- Request validation using Zod schemas shared between client and server
- CORS and security middleware configured for production deployment

### Real-time Features
- **Live Tracking**: Provider location updates and status changes
- **Service Matching**: Automatic provider assignment based on service type and availability
- **Status Updates**: Real-time request status progression (pending → accepted → en_route → completed)

### Mobile-First Design
- Responsive design optimized for mobile devices
- Touch-friendly interface with modal-based interactions
- Geolocation integration for automatic user location detection
- QR code generation for payment processing

## External Dependencies

### Core Framework Dependencies
- **React Ecosystem**: React 18, React DOM, React Router (wouter)
- **Build Tools**: Vite with TypeScript support and React plugin
- **Development**: tsx for TypeScript execution, esbuild for production builds

### UI Component Libraries
- **Design System**: Complete shadcn/ui component library
- **Primitive Components**: Radix UI primitives for accessibility
- **Icons**: Lucide React icon library
- **Styling**: Tailwind CSS with class-variance-authority for component variants

### Backend Infrastructure
- **Database**: Neon Database PostgreSQL with Drizzle ORM
- **Session Management**: connect-pg-simple for PostgreSQL session storage
- **Validation**: Zod for runtime type checking and validation
- **Utilities**: date-fns for date manipulation

### Development & Deployment
- **Replit Integration**: Vite plugins for Replit development environment
- **Error Handling**: Runtime error overlay for development
- **Code Cartography**: Replit cartographer for code exploration
- **Font Loading**: Google Fonts integration (Architects Daughter, DM Sans, Fira Code, Geist Mono)

### Service Integration Points
- **Geolocation API**: Browser geolocation for user positioning
- **Payment Processing**: QR code generation infrastructure (placeholder implementation)
- **Real-time Updates**: Polling-based provider status updates
- **Maps Integration**: Prepared for maps API integration (coordinates stored for future use)