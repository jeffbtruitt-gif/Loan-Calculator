[README.md](https://github.com/user-attachments/files/26860602/README.md)
# Jefe Bank — Loan Calculator

An iPhone-styled HTML loan calculator with trade-in support and an amortization schedule.

## Files

```
index.html                    # The app
manifest.json                 # PWA manifest (icon + theme metadata)
Jefe_Bank_Logo.png            # In-app header logo (rectangular with text)
Jefe_bank_iphone_logo.png     # Home-screen icon (rounded square, 1024x1024 source recommended)
```

Drop all four files in the same directory. The app references both logos by filename:

- `index.html` → `<img src="Jefe_Bank_Logo.png">` in the header
- `index.html` → `<link rel="apple-touch-icon" href="Jefe_bank_iphone_logo.png">` for the home-screen icon

## Adding to iPhone home screen

1. Host the files somewhere (GitHub Pages, Netlify, Replit, or a local server)
2. Open the URL in Safari on iPhone
3. Tap the Share button → **Add to Home Screen**
4. The rounded-square Jefe Bank icon appears on your home screen
5. Launching it opens the calculator in full-screen standalone mode (no Safari chrome)

## Features

- Purchase price, trade-in value, trade-in owed (for upside-down trades), cash down
- Rate and term inputs
- Net trade equity display (turns red if underwater)
- Live calculation on input change
- Monthly payment, amount financed, total interest, total paid
- Yearly / monthly amortization schedule with sticky header
- Navy `#1a2942` + gold `#C9A961` theme pulled from the logo

## Math

```
Amount financed = Purchase price − (Trade-in value − Trade-in owed) − Cash down
Monthly payment = P × [r(1+r)^n] / [(1+r)^n − 1]
```

where `P` is the amount financed, `r` is the monthly rate, `n` is the number of monthly payments.

## Notes

- The 16px input font size is intentional — iOS Safari zooms inputs below 16px on focus.
- `apple-mobile-web-app-capable` + `black-translucent` status bar gives the standalone-app look when launched from the home screen.
- No external dependencies; works offline once cached.
