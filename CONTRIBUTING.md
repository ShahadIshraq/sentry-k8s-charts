# Contributing to Sentry K8s Charts

Thank you for your interest in contributing to the Sentry Kubernetes Helm charts project! This document provides guidelines and instructions for contributing.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion for improvement:

1. Check if the issue already exists in the issue tracker
2. If not, create a new issue with a clear description including:
   - What you expected to happen
   - What actually happened
   - Steps to reproduce
   - Version information (Kubernetes, Helm, chart versions)

### Contributing Code

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-new-feature`
3. Make your changes
4. Update documentation as needed
5. Test your changes thoroughly
6. Commit your changes: `git commit -am 'Add some feature'`
7. Push to the branch: `git push origin feature/my-new-feature`
8. Submit a pull request

### Pull Request Process

1. Update the README.md or documentation with details of changes if appropriate
2. Update the version numbers in Chart.yaml files following [semver](https://semver.org/)
3. Your PR will be reviewed by maintainers, who may request changes
4. Once approved, your PR will be merged

## Development Guidelines

### Helm Chart Standards

- Follow the [Helm best practices](https://helm.sh/docs/chart_best_practices/)
- Use consistent indentation (2 spaces)
- Provide detailed comments in templates
- Include appropriate NOTES.txt files

### Testing

Before submitting a PR, ensure:

1. Charts pass linting: `helm lint charts/*`
2. Templates render correctly: `helm template charts/*`
3. Charts install successfully in a test environment
4. Any new functionality works as expected

### Documentation

- Update README.md files for any chart that changes
- Document all values in values.yaml with clear descriptions
- Update the main documentation if adding new features

## Code of Conduct

Please be respectful and inclusive in your interactions with the community. We are committed to providing a welcoming environment for all contributors.
