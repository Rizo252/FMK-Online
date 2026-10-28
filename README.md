# Football Market Kings — Online Multiplayer Foundation

This is a **new online multiplayer prototype**, not a network-enabled copy of the complete Historical Edition. The earlier single-file offline game is unchanged. This project has a server-authoritative room system, real join codes, WebSocket synchronisation, shared sealed bids, headline auction, shared squads and six-fixture tournaments. It uses the supplied historical player dataset and hides real identities until sale. It has **no overall ratings**.

## Run on a computer
1. Install Node.js 20 or later.
2. Open a terminal in this folder.
3. Run `npm install` and then `npm start`.
4. Visit `http://localhost:3000`. Friends on the same local network can use your local IP and port 3000 if allowed by your firewall.

## Put it online for free (Render)
1. Create a GitHub repository and upload the files in this folder **at the repository root**, including `server.js`, `players.json`, `package.json`, and the `public` directory.
2. In Render, choose **New → Web Service** and connect the repository.
3. Select the free instance if available; use Build Command `npm install` and Start Command `npm start`.
4. Once deployed, open the `https://...onrender.com` address, create a room and share the invitation URL or six-character code.
5. **Do not upload this server folder to Netlify Drop**; Netlify Drop only hosts static files and cannot run this WebSocket server.

Free hosting may sleep when idle, disconnect active rooms during redeploys, and have usage limits. Rooms are stored **in memory** and will disappear on server restart. Use this as a live multiplayer test, not a production service.

## Current limitations
- This is a distinct online prototype; it does not yet contain every offline game's feature (full match broadcast, advanced tactics, private trades, true random-event consequences, player scouting, historical profit logic, final liquidation, or persistent rooms).
- The room code and reconnect token are stored in browser session storage; a reload in the same tab can reconnect while the server remains running.
- Human managers cannot join after the campaign starts. AI fills empty seats at start.
- Matches are simulated by the server, but currently advance manually in ten-minute steps and only reveal the score at full time.
- Historical player values are sourced from the provided dataset when present and approximated when missing; the data has not been independently verified.
- Keep the existing offline Historical Edition for feature-complete solo play while online functionality is developed.
