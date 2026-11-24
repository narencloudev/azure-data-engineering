# ADF Git Integration and CI/CD

## Git integration
ADF can connect its authoring environment to a supported Git repository so developers can work with branches, review changes, and collaborate.

## Collaboration flow
1. Work in a feature branch.
2. Validate and test pipeline changes.
3. Review and merge to the collaboration branch.
4. Publish or deploy artifacts through the team's release process.

## CI/CD
A deployment process promotes ADF artifacts across environments such as development, test, and production. Environment-specific values should be parameterized rather than embedded in pipeline logic.

## Key concepts
- Collaboration branch
- Feature branch
- Pull request
- Publish branch / deployment artifacts
- ARM template or supported deployment mechanism
- Environment parameters and linked-service configuration

## Best practices
- Keep source control as the reviewable source of truth.
- Separate development and production credentials.
- Use approvals for production deployment.
- Test triggers and integration runtime configuration after deployment.

## Practice
Draw a dev → test → production deployment workflow and list what must differ by environment.
