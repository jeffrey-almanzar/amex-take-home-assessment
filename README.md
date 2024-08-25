## Task 1 - configure and document the repository

Note that I prioritized and completed `Task 2`.  As part of `Task 1`, I documented the essential things that I'd do to get this project production-ready:

**1. Version control: optimize the project to be stored on a remote Git repository**

Version control is needed for multiple reasons, such as code changes tracking, collaboration, rollbacks, backups, code reviews, and more. At the very least, we should:

- Create a new local git repository 
- Create a `.gitignore` file to ignore files and directories that don't need to be tracked (e.g. `node_modules`, `dist`, etc.)
- Push the local repo to a central, remote repository to make it available to all the developers (`GitHub`, `GitLab`, `Bitbucket`, etc). 

**2. Setup testing**

Testing is crucial to catch issues early and reduce the number of bugs in a production application. Here are some recommendations: 

- Use Jest for unit and integration testing.
- Use Enzyme for testing React components.
- Use Cypress.io for end-to-end testing and testing the application in a real browser environment.

**3. Ensure code quality and consistency**

- Setup ESLint with appropriate rules to catch errors and enforce coding standards.
- Integrate ESLint and Prettier for code formatting to maintain a consistent style across the codebase.
- Use Husky and lint-staged for Git hooks to enforce linting and formatting before commits, ensuring code quality is maintained.

**4. Security**

- Use `dotenv` to manage environment variables. This ensures sensitive information (e.g., API keys) is not hardcoded in the source code
- Ensure that any user input is properly sanitized and validated to prevent XSS or injection attacks.
- Implement Content Security Policy (CSP) headers to protect against cross-site scripting attacks.

**5. Continuous Integration and Deployment (CI/CD)**

Setup CI/CD for faster development cycles, higher consistency, and improved reliability:

- CI Setup for automated testing, linting, and building the project on each commit. (e.g. `GitLab CI/CD`, `GitHub Actions`)
- CD Pipeline for automated deployment to specific environments on successful builds. (e.g. `Netlify`, `Vercel`, `AWS`)

**6. Performance Optimization**

Profile the application using Google Lighthouse or a similar tool to get some insights about the current performance of the app. Based on the findings, consider:
   - Code Splitting: use dynamic imports and React’s lazy loading to split code and reduce initial load times.
   - Memoization: use React.memo, useMemo, and useCallback to prevent unnecessary re-renders and optimize performance.
   - Service Workers: to enable Progressive Web App (PWA) features, allowing the app to work offline and load faster.

**7. Accessibility**

The ADA requires that businesses open to the public provide full and equal enjoyment of their goods to people with disabilities. Therefore, we need to meet WCAG standards.  

- Run an accessibility audit using a tool like Axe or Lighthouse.
- Make sure to use semantic HTML and fix the errors found in the audit report.

**8. Documentation**

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
