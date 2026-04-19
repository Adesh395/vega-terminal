Take a screenshot of the VEGA Terminal and analyze the result.

Steps:
1. Check if the dev server is running: `curl -s -o /dev/null -w "%{http_code}" http://localhost:3000`
2. If not running (not 200), start it: `node serve.mjs` in background, wait 1s
3. Run: `node screenshot.mjs http://localhost:3000 $ARGUMENTS`
4. Read the latest screenshot from `./temporary screenshots/`
5. Describe what you see — note any layout issues, color mismatches, or visual bugs

Use label argument to tag the screenshot, e.g. `/project:screenshot dashboard` saves as `screenshot-N-dashboard.png`
