# DriveEase — Car Rental Website

A front-end car rental web app built with plain HTML, CSS, and vanilla JavaScript. No frameworks, no backend — session state is handled entirely in the browser with `sessionStorage`.

## Pages

| File             | Purpose                                                                 |
|-------------------|--------------------------------------------------------------------------|
| `index.html`      | Landing page — hero section, feature highlights, and a call to action.   |
| `catalogue.html`  | Browsable fleet of 6 cars with specs and daily pricing. Open to everyone, no login required. |
| `login.html`      | Sign-in form collecting First Name, Surname, Phone Number, Email, Age, and Password. |
| `register.html`   | Booking confirmation page — pickup/return dates and pickup/drop-off locations for a selected car. |

## User Flow

1. **Browse freely** — Anyone can open `catalogue.html` from the nav and look through the fleet without signing in.
2. **Rent a car** — Clicking **Rent Now** on any car sends you to the booking page (`register.html?car=<name>`), pre-filled with the selected car.
3. **Sign in** — The booking page requires a session; if you're not signed in, you're redirected to `login.html` to provide your details first.
4. **Confirm booking** — Once signed in, fill in pickup date, return date, pickup location, and drop-off location. Submitting shows a confirmation summary of the full booking.

## Features

- Responsive card-based catalogue with hover effects
- Client-side form validation (e.g. return date must be after pickup date, password confirmation on signup flows)
- Session persistence via `sessionStorage` (`loggedIn`, `userName`, `userSurname`, `userPhone`, `userAge`)
- Car selection is passed between pages via a URL query parameter (`?car=`)
- Auth banner on the catalogue greets signed-in users by name
- No external dependencies — pure HTML/CSS/JS, works by opening the files directly in a browser

## Project Structure

```
├── index.html         # Home / landing page
├── catalogue.html     # Car fleet listing
├── login.html         # Sign-in form
├── register.html      # Booking details & confirmation
└── images/            # Car photos (corolla.jpg, crv.jpg, bmw.jpg, mustang.jpg, elantra.jpg, mercedes.jpg)
```

## Running Locally

No build step or server required:

1. Download/clone the project folder.
2. Make sure an `images/` folder sits alongside the HTML files with the car photos referenced in `catalogue.html`.
3. Open `index.html` in any modern browser.

## Notes & Limitations

- This is a front-end prototype: there is no real backend, database, or authentication — signing in simply stores your entered details in `sessionStorage` for the current browser tab session.
- Data does not persist across browser restarts or tabs (by design, since it uses `sessionStorage` rather than `localStorage` or a server).
- Prices, cars, and specs are static/hard-coded in `catalogue.html`.

## Possible Next Steps

- Persist bookings (e.g. `localStorage` or a real backend/database)
- Add a "My Bookings" page to view past/upcoming reservations
- Replace free-text pickup/drop-off fields with a location picker
- Add server-side validation and real authentication
