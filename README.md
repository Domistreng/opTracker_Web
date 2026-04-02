# opTracker — Web App

A browser-based companion for competitive Bandai TCG players. Log your deck lists,
track tournament matchups, and explore the wider player community.

---

## Development Checklist

### Authentication & Account
- [ ] User registration (email/password)
- [ ] User login
- [ ] JWT session management
- [ ] Password reset flow
- [ ] Privacy settings (public/private profile toggle)
- [ ] Granular privacy controls (e.g., hide deck lists until after an event)

### Deck Lists
- [ ] Create new deck list
- [ ] Edit existing deck list
- [ ] Delete deck list
- [ ] Set deck list visibility (public/private)
- [ ] QR code generation for deck list sharing
- [ ] QR code display modal for sharing at events

### Event & Matchup Logging
- [ ] Log a new event (name, date, format)
- [ ] Log individual match results per event
- [ ] Record opponent's leader/deck
- [ ] Win/loss/draw tracking
- [ ] View match history by event
- [ ] Offline support (PWA) — queue matchup logs locally when no internet connection
- [ ] Auto-sync queued logs when internet connection is restored
- [ ] Visual indicator showing pending unsynced logs

### Stats & Analytics
- [ ] Win rate by leader
- [ ] Matchup win rates vs opponent leaders
- [ ] Event placement history
- [ ] Performance trends over time

### Player Lookup & Social
- [ ] Search for players by username
- [ ] View other players' public profiles
- [ ] View other players' public deck lists
- [ ] View other players' public tournament matchups
- [ ] Send/accept friend requests
- [ ] Friends list view

### Notifications
- [ ] In-app notification center
- [ ] Notify when a friend logs a new event result
- [ ] Notify when a friend posts a new deck list
- [ ] Notify when event signups go live (local and international)
- [ ] Notify when new product preorders go live on official Bandai sites
- [ ] Notification preferences settings (per-category toggles)
- [ ] Browser push notification support (via Service Worker)

### Top Decks (Read-Only, Backend-Managed)
- [ ] View deck lists that topped major international events
- [ ] View matchups associated with those top-performing lists
- [ ] Filter by event, format, or leader

### Event Calendar
- [ ] Browse upcoming local/regional events
- [ ] Browse upcoming international events
- [ ] Event signup status (open / coming soon / closed)
- [ ] Opt-in alerts per event for when signups open
- [ ] External registration links

### Product Preorder Tracker
- [ ] List upcoming Bandai TCG product releases
- [ ] Track preorder availability status per retailer
- [ ] Opt-in alerts per product when preorders go live
- [ ] Link to official preorder pages when live

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | *(e.g., React / Next.js / Vue)* |
| Language | *(e.g., TypeScript)* |
| Auth | JWT via shared backend |
| API | Shared REST/GraphQL backend |
| Styling | *(e.g., Tailwind CSS)* |
| Offline Queue | Service Worker + IndexedDB |
| Notifications | Browser Push API via Service Worker |

---

## Related Repos

- [opTracker Backend](../optracker-backend)
- [opTracker Mobile App](../optracker-mobile)

---

## Getting Started

```bash
# Install dependencies
npm install

# Run dev server
npm run dev
```

---

## Notes

- There is no card lookup feature in the web app. Card search is available on mobile only.
- Offline matchup logs are stored in IndexedDB via a Service Worker and synced automatically
  on reconnection. Conflicts (e.g., duplicate submissions) will be handled server-side.
- Top deck data is managed exclusively through the backend and is not user-submitted.
- Preorder and event notification data is managed through the backend and sourced from
  official Bandai channels.