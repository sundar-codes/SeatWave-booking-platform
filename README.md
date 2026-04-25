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

## Environment Variables

Create a `.env` file in the project root with:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
VITE_ADMIN_EMAILS=admin1@example.com,admin2@example.com
```

Notes:

- `VITE_ADMIN_EMAILS` is optional, but it is used to recognize admin accounts by email.
- The app now throws a clear startup error if the Supabase URL or anon key is missing.

## Getting Started

1. Install dependencies:

```bash
npm install
```

2. Start the development server:

```bash
npm run dev
```

3. Open the local Vite URL shown in the terminal, usually `http://localhost:5173`.

## Available Scripts

```bash
npm run dev
npm run build
npm run preview
npm run lint
npm run typecheck
```

## Feature Overview

### Event Discovery

- Search events by title or description
- Filter by category
- View pricing, location, date, and seat availability badges

### Authentication

- Email/password sign-up and login through Supabase
- Separate user and admin login modes
- Protected routes for dashboard and admin pages
- Persistent sessions handled in auth context

### Booking Experience

- Event details page shows reviews and booking entry
- Showtime helpers support theatre, date, format, and language-based browsing
- Seat selection flow uses show-specific seat inventory
- Booking utilities update both show-level and event-level seat counts

### User Dashboard

- View active and cancelled bookings
- Cancel bookings directly from the dashboard
- Review booked events
- Edit or delete existing reviews

### Admin Dashboard

- Booking and revenue summary cards
- Revenue by event
- Tickets booked by event
- Recent bookings table
- Event-level analytics and remaining seats overview

### Offline-Friendly Fallbacks

- Booking and review actions can be mirrored locally
- If some Supabase reads fail, the app can still recover from mirrored local data for a better experience

## Supabase Data Used

The app currently works with these main entities:

- `events`
- `bookings`
- `reviews`
- `shows`
- seat data associated with shows

Your Supabase project should provide the matching tables and columns expected by the files in `src/lib/supabase.ts` and `src/lib/bookingExperience.ts`.

## Notes

- The UI theme has moved away from the older red-accent TicketHub styling. The current app uses the SeatWave brand with slate, sky, and amber tones.
- The README previously described a simpler ticket flow. The current version includes showtime browsing, seat-map booking, review management, and admin analytics.

## Future Improvements

- Payment integration
- Email confirmations and reminders
- Better admin event management tools
- Stronger offline sync instead of local-only mirroring
- Improved automated validation and test coverage

## License

This project is available under the MIT License.
