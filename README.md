# .github

Shared GitHub Actions workflow templates for the BrowserMesh ecosystem.

## Available Templates

### `ci-node.yml`
Reusable CI workflow for single-package Node.js repos (npm).

```yaml
# In your repo's .github/workflows/ci.yml
name: CI
on: [push, pull_request]
jobs:
  test:
    uses: johnhenry/.github/.github/workflow-templates/ci-node.yml@main
    with:
      node-version: '22'
      test-command: 'npm test'
```

### `ci-pnpm.yml`
Reusable CI workflow for pnpm monorepos (like raijin).

```yaml
name: CI
on: [push, pull_request]
jobs:
  test:
    uses: johnhenry/.github/.github/workflow-templates/ci-pnpm.yml@main
    with:
      node-version: '22'
      pnpm-version: '9'
```

### `publish-npm.yml`
Reusable workflow for publishing to npm on version tags.

```yaml
name: Publish
on:
  push:
    tags: ['v*']
jobs:
  publish:
    uses: johnhenry/.github/.github/workflow-templates/publish-npm.yml@main
    with:
      node-version: '22'
    secrets:
      npm-token: ${{ secrets.NPM_TOKEN }}
```

## Repos Using These Templates

- [browsermesh-primitives](https://github.com/johnhenry/browsermesh-primitives)
- [browsermesh-netway](https://github.com/johnhenry/browsermesh-netway)
- [browsermesh-pod](https://github.com/johnhenry/browsermesh-pod)
- [wsh-upon-star](https://github.com/johnhenry/wsh-upon-star)
- [andbox](https://github.com/johnhenry/andbox)
- [ai-matey-middleware-andbox](https://github.com/johnhenry/ai-matey-middleware-andbox)
- [raijin](https://github.com/johnhenry/raijin)
- [browsermesh-servers](https://github.com/johnhenry/browsermesh-servers)

## License

MIT
