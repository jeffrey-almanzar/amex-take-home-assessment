## Task 1 - configure and document the repository

These are the essential things that I'd do to get this project production-ready:

**Optimize the project to be stored on a remote Git repository**

Version control is essential in any software development project since it allows tracking changes, facilities collaboration, allows rollbacks, provides backups, supports code reviews, and more. At the very least, we should:

- create a new local git repository 
- create a .gitignore file to ignore files and directories that don't need to be tracked: node_modules, dist, etc.

**Setup testing**

Testing is crucial to reduce the number of bugs in a production application. Here are some recommendations: 

- Jest: for unit and integration testing.
- Enzyme: For testing React components.
- Cypress.io: For testing the application in a real browser environment.

**Ensure code quality and consistency**

- ESLint: Set up ESLint with appropriate rules to catch errors and enforce coding standards.
- Prettier: Integrated for code formatting to maintain a consistent style across the codebase.
- Husky & lint-staged: Git hooks to enforce linting and formatting before commits, ensuring code quality is maintained.

**Security**

- Environment Variables: use `dotenv` to manage environment variables. This ensures sensitive information (e.g., API keys) is not hardcoded in the source code
- Sanitization and Validation: ensure that any user input is properly sanitized and validated to prevent XSS or injection attacks.
- Content Security Policy (CSP): implement CSP headers to protect against cross-site scripting attacks.

**Continuous Integration and Deployment (CI/CD)**

- CI Setup: for automated testing, linting, and building the project on each commit. Examples: `GitLab CI/CD`, `GitHub Actions`, etc.
- CD Pipeline: automated deployment to environments on successful builds. (e.g., Netlify, Vercel, AWS)

**Accessibility**

- Accessibility Audits: use tools like Axe or Lighthouse to ensure that the application meets accessibility standards (e.g., WCAG).
- Semantic HTML and ARIA: ensure the application uses semantic HTML elements and appropriate ARIA attributes.

**Monitoring and Error Handling**

- Error Boundaries: implement React error boundaries to catch and display fallback UI for component errors.
- Logging and Monitoring: use tools like Sentry or LogRocket to track and log errors and performance metrics in production.

**Performance Optimization**

- Profile the application using Google Lighthouse or a similar tool to get some insights about the current performance of the app. Based on the findings, these are a few things to consider:
   - Code Splitting: use dynamic imports and React’s lazy loading to split code and reduce initial load times.
   - Memoization: use React.memo, useMemo, and useCallback to prevent unnecessary re-renders and optimize performance.
   - Service Workers: to enable Progressive Web App (PWA) features, allowing the app to work offline and load faster.

**Documentation**

I'd document the top level file structure, how to run the application, among other things to make sure that a new developer can get up to speed quickly.  



## Task 2 - complete the caching fetch library

I've completed the subtasks defined in `caching-fetch-library/cachingFetch.ts`. To test my code, follow the following steps:

**1. Run the updated application**:

```
git clone https://github.com/jeffrey-almanzar/amex-take-home-assessment.git
cd amex-take-home-assessment && npm i && npm start
```

**2. Visit the corresponding URLs**:

- http://localhost:3000
- http://localhost:3000/appWithSSRData
- http://localhost:3000/appWithoutSSRData
