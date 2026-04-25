# SeatWave-booking-platform
A high-performance Event Ticketing &amp; Management Platform built with React, TypeScript, and Supabase. Features a multi-role architecture, interactive seat selection, and a comprehensive admin analytics dashboard.
# SeatWave

SeatWave is a React + TypeScript event ticket booking app built with Vite, Tailwind CSS, and Supabase. It lets users browse events, choose showtimes, pick seats, manage bookings, and leave reviews, while admins can view booking and revenue analytics.

## Highlights

- Browse events with category filters and search
- View event details, reviews, and showtime availability
- Continue from an event into seat selection for a specific show
- Support user and admin sign-up/login flows
- Manage bookings from a personal dashboard
- Cancel active bookings and restore seat inventory
- Leave, edit, and delete event reviews
- View admin analytics for bookings, tickets, revenue, and shows
- Show toast feedback for important actions
- Fall back to locally mirrored booking/review data when some requests fail

## Tech Stack

- React 18
- TypeScript
- Vite
- Tailwind CSS
- Supabase Auth and Database
- React Router
- Lucide React

## App Routes

- `/` - landing page with event discovery
- `/login` - user/admin login
- `/signup` - user/admin registration
- `/event/:id` - event details, reviews, and showtime entry
- `/event/:id/show/:showId` - seat selection and booking flow
- `/dashboard` - protected user dashboard
- `/admin` - protected admin dashboard

## Current Project Structure

```text
src/
|-- components/
|   |-- seat/
|   |-- showtime/
|   |-- Footer.tsx
|   |-- Navbar.tsx
|   |-- ProtectedRoute.tsx
|   |-- ReviewCard.tsx
|   |-- SeatBadge.tsx
|   |-- StarRating.tsx
|   `-- Toast.tsx
|-- contexts/
|   |-- AuthContext.tsx
|   |-- ToastContext.tsx
|   `-- useAuth.ts
|-- lib/
|   |-- bookingExperience.ts
|   |-- eventPresentation.ts
|   |-- localMirror.ts
|   `-- supabase.ts
|-- pages/
|   |-- AdminDashboard.tsx
|   |-- Dashboard.tsx
|   |-- EventDetails.tsx
|   |-- Home.tsx
|   |-- Login.tsx
|   |-- SeatSelection.tsx
|   `-- Signup.tsx
|-- App.tsx
|-- index.css
`-- main.tsx
```
