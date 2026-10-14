# Maintenance Mode Guide

## Overview
The maintenance mode allows you to quickly display a professional maintenance page to all visitors while you update the site. When enabled, all users will see the maintenance page instead of the normal site.

## How to Enable Maintenance Mode

1. Open the file: `apps/web/src/utils/maintenanceMode.js`
2. Change this line:
   ```javascript
   export const MAINTENANCE_MODE = false;
   ```
   to:
   ```javascript
   export const MAINTENANCE_MODE = true;
   ```
3. Reload the app (the changes will take effect immediately)

## How to Disable Maintenance Mode

1. Open the file: `apps/web/src/utils/maintenanceMode.js`
2. Change this line:
   ```javascript
   export const MAINTENANCE_MODE = true;
   ```
   to:
   ```javascript
   export const MAINTENANCE_MODE = false;
   ```
3. Reload the app (the site will return to normal)

## Maintenance Page Features

- **Professional Design**: Matches delfinitx branding with purple accent color (#7132F5)
- **Clean Layout**: Centered card with animated background elements
- **Responsive**: Works perfectly on mobile, tablet, and desktop
- **SEO Friendly**: Includes `noindex, nofollow` meta tag to prevent search engine indexing
- **Status Indicator**: Shows "Maintenance in progress" with animated pulse
- **Branding**: Includes delfinitx copyright and branding

## Maintenance Page Content

The page displays:
- "Site Under Maintenance" heading
- "We are updating the site for the Blog of recipes for cakes and sweets. Come back soon!" message
- Maintenance status indicator
- Professional footer with delfinitx branding

## Files Modified

- `apps/web/src/pages/MaintenancePage.jsx` - Maintenance page component
- `apps/web/src/utils/maintenanceMode.js` - Maintenance mode toggle
- `apps/web/src/App.jsx` - App routing logic to show maintenance page when enabled

## Notes

- The maintenance page is shown to ALL users, regardless of authentication status
- No routes or pages are accessible when maintenance mode is enabled
- The toggle is simple and can be changed in seconds
- Changes take effect immediately after app reload
