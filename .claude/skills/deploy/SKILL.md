Run the full deploy pipeline for this project: tests → production build → staging push.

## Steps

1. **Run tests**
   ```bash
   npm run lint
   ```
   If linting fails, stop and report the errors. Do not proceed.

2. **Build production bundle**
   ```bash
   npm run build
   ```
   If the build fails, stop and report the errors. Do not proceed.

3. **Push to staging**
   ```bash
   git push origin main:staging
   ```
   Report the result to the user.

After each step, confirm success before moving to the next. If any step fails, clearly state which step failed and what the error was.
