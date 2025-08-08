### Commit Message Convention

Use a pattern like:

```
git commit -m "<type>-<component>:<detail>"
```

Where:

- `<type>` indicates what kind of change you're making
- `<component>` specifies which part of your architecture you're modifying
- `<detail>` provides more specific information about the change

### Types

- `feat` - New feature
- `fix` - Bug fix
- `refactor` - Code change that neither fixes a bug nor adds a feature
- `docs` - Documentation changes
- `style` - Formatting, missing semi-colons, etc; no code change
- `test` - Adding or refactoring tests
- `chore` - Updating build tasks, package manager configs, etc

### Components (based on  architecture)

- `model` - Data model changes
- `contract` - Interface and API contract changes
- `controller` - Endpoint controller changes
- `service` - Service implementation
- `repo` - Repository implementation
- `util` - Utilities and helpers

### Examples

```
git commit -m "feat-controller:AdsController"
git commit -m "fix-model:UserEntity"
git commit -m "refactor-service:PaymentProcessing"
git commit -m "feat-contract:OrderManagementInterface"
```
