# Feed Window

A small offline-friendly page that scores each hour of the day for whitetail, wild hog, turkey, bass, catfish and crappie. It uses light (dawn, dusk, night), the barometric pressure trend, temperature, wind, rain, and a small bonus for moon periods.

It is one HTML file with no build step and no accounts. Your log and saved spots stay in the browser on your phone.

## Put it on your phone

1. Open the page in Safari (iPhone) or Chrome (Android).
2. iPhone: Share, then **Add to Home Screen**. Android: menu, then **Install app** or **Add to Home screen**.
3. Open it once with a signal and tap **Download forecast for offline**. That saves about nine days of hourly weather.
4. In the field, with no signal, open it from the home screen. Sun, moon, scores and your log all work. The forecast is as fresh as your last download.

Download again before each trip. Forecasts older than a day lose accuracy, especially the pressure trend.

## Publish with GitHub Pages

1. Create a repository and upload every file in this folder (`index.html`, `sw.js`, `manifest.json`, the three PNG icons, and this README).
2. Settings, then Pages, then deploy from the `main` branch, root folder.
3. After a minute the page is live at `https://YOUR-NAME.github.io/REPO-NAME/`.

GitHub Pages on a free account needs a public repository. Nothing private is in these files: spots, the log and any coordinates you enter are saved only in each phone's browser, not in the repo.

When you change `index.html`, also change `CACHE = 'feed-window-v1'` in `sw.js` (for example to `v4`) so phones fetch the new version.

## How the score works

Each hour gets a score from 0 to 100.

| Part | Roughly how many points |
| --- | --- |
| Light: dawn, dusk, midday or night, per species | up to 38 |
| Pressure trend over 6 hours, per species | up to 14 |
| Air temperature comfort range, per species | up to 12 |
| Wind speed and heavy rain | up to −12 each |
| Wrong wind direction for your stand (whitetail and hog, only if you mark good winds) | −10 |
| Moon over or under the spot, moonrise, moonset | up to 9 |
| Near new or full moon | up to 4 |

Labels: 70 and up is Prime, 55 to 69 Good, 40 to 54 Fair, below 40 Slow.

The moon is capped at 13 points on purpose. Studies of deer movement and fish feeding disagree on whether the moon matters much. The pressure and temperature weights are educated guesses from published studies and hunting and fishing guidance, not a validated model. The field log is how you test them: after about eight logged outings the page compares your results at high scores against low scores.

Fish scores use air temperature because water temperature is not in the forecast.

## Data

Weather comes from [Open-Meteo.com](https://open-meteo.com/) (free for non-commercial use, attribution required). Your coordinates are sent to Open-Meteo only when you tap Download forecast. If you use the airport option, the airport code (not your location) is sent to the [Aviation Weather Center](https://aviationweather.gov/), and its actual readings replace the forecast for the hours they cover. Sun and moon positions are calculated on the device using the SunCalc method (MIT license), so they need no signal.

## Not legal advice

The scores show when animals are likely to be active. They do not show legal shooting hours or seasons. Check your county and state rules.
