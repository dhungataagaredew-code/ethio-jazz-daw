# Ethio-Jazz DAW — Agent Operation Guide

This repository is designed to support collaborative development using AI agents and automated workflows.

**Canonical repository**: `https://github.com/dhungataagaredew-code/ethio-jazz-daw`

## First Decide the Operation

Choose exactly one operation:

1. **Setup or Install** — Follow "Getting Started" section below
2. **Inspect or Review** — Read `README.md`, `package.json`, and project structure documentation
3. **Development** — Follow "Development Workflow" section
4. **Testing** — Follow "Testing & Validation" section
5. **Release or Deploy** — Follow "Maintainer Operations" section

## Project Architecture

The Ethio-Jazz DAW follows a modular architecture:

```
ethio-jazz-daw
  ├── src/
  │   ├── core/          # DAW core functionality
  │   ├── audio/         # Audio synthesis & processing
  │   ├── ui/            # React UI components
  │   └── utils/         # Helper utilities
  ├── tests/             # Test suite
  ├── docs/              # Documentation
  ├── examples/          # Example projects
  └── config/            # Configuration files
```

### Technology Stack

- **Frontend**: React 18.x
- **Audio Engine**: Web Audio API + Tone.js
- **Build Tool**: Webpack 5.x
- **Testing**: Jest
- **Linting**: ESLint
- **Formatting**: Prettier
- **Package Manager**: npm
- **Node.js**: v16+ required

## Installation & Setup

### Prerequisites

```bash
# Verify Node.js version (16.x or higher required)
node --version

# Verify npm
npm --version

# Verify Git
git --version
```

### 1. Clone Repository

```bash
git clone https://github.com/dhungataagaredew-code/ethio-jazz-daw.git
cd ethio-jazz-daw
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Verify Installation

```bash
npm run lint
npm test
```

### 4. Start Development Server

```bash
npm run dev
```

Access at `http://localhost:3000`

## Development Workflow

### Create a Feature Branch

```bash
git checkout -b feature/your-feature-name
```

### Instrument Modules

Available instruments in `/src/audio`:

- **Lyre** - African string instrument
- **SpikeFiddle** - Bowed spike-bodied fiddle
- **BambooFlute** - Bamboo wind instrument
- **Vibraphone** - Jazz vibraphone with vibrato
- **UprightBass** - Deep bass instrument
- **FrameDrum** - Rhythmic percussion
- **HandClaps** - Hand percussion

### Code Quality Checks

```bash
# Lint code
npm run lint

# Format code
npm run format

# Run tests
npm test

# Watch mode for development
npm run test:watch
```

### Building

```bash
# Development build
npm run dev:build

# Production build
npm run build
```

## Testing & Validation

### Test Structure

Tests should be located in `/tests` with structure:
- `tests/core/` — Core functionality tests
- `tests/audio/` — Audio synthesis tests
- `tests/ui/` — UI component tests
- `tests/integration/` — Integration tests

### Running Tests

```bash
# Run all tests
npm test

# Run specific test file
npm test tests/audio/lyre.test.js

# Run with coverage
npm test -- --coverage

# Watch mode
npm run test:watch
```

### Test Requirements

- All new features must include tests
- Minimum 80% code coverage
- All tests must pass before PR submission
- Integration tests required for audio engine changes

## Pull Request Process

1. Create feature branch from `develop`
2. Make changes and commit with meaningful messages
3. Run all tests and linting locally
4. Push to your fork
5. Submit PR with description of changes
6. Address review feedback
7. Merge only after CI passes and review approved

### PR Checklist

- [ ] Tests written and passing
- [ ] Code linted and formatted
- [ ] Documentation updated
- [ ] Commit messages are clear
- [ ] No breaking changes to public API
- [ ] CHANGELOG.md updated

## Maintainer Operations

### Version Management

Current version: See `package.json`

Increment according to Semantic Versioning:
- **PATCH**: Bug fixes
- **MINOR**: New features, backward compatible
- **MAJOR**: Breaking changes

### Release Process

1. Update version in `package.json`
2. Update `CHANGELOG.md`
3. Run full test suite: `npm test`
4. Build production: `npm run build`
5. Create Git tag: `git tag v0.x.x`
6. Push tag: `git push origin v0.x.x`
7. Create GitHub Release with notes

### Publishing

```bash
# Publish to npm (requires npm account)
npm publish
```

## CI/CD Workflow

GitHub Actions automatically:

- Runs ESLint on all commits
- Runs Jest test suite
- Runs on Node.js 16.x and 18.x
- Builds production bundle
- Validates with multiple Node versions

See `.github/workflows/ci.yml` for configuration.

## Safety Boundaries

**Do not:**
- Commit credentials or API keys
- Modify Git remotes without authorization
- Push to main branch directly
- Deploy without CI passing
- Remove or break existing instrument modules
- Change audio API without version bump

**Do:**
- Follow existing code style
- Write meaningful commit messages
- Keep documentation updated
- Test thoroughly before submitting PR
- Use feature branches for all work

## Troubleshooting

### Audio Not Working

```bash
# Verify audio dependencies
npm list tone

# Check browser console for errors
# Ensure system audio is unmuted
# Test with simple instrument in browser DevTools
```

### Build Errors

```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install

# Clean webpack cache
rm -rf dist/

# Rebuild
npm run build
```

### Test Failures

```bash
# Run tests with verbose output
npm test -- --verbose

# Run specific test file
npm test tests/audio/lyre.test.js

# Update snapshots if needed
npm test -- -u
```

## Documentation

- `README.md` - Project overview
- `docs/getting-started.md` - User guide
- `docs/architecture.md` - Technical architecture
- `docs/api.md` - API reference
- `CONTRIBUTING.md` - Contribution guidelines
- `CODE_OF_CONDUCT.md` - Community standards

## Support & Questions

- Open an issue for bugs
- Check existing issues before opening new ones
- Use discussions for feature requests
- Follow the issue templates

---

**Last Updated**: August 2026
**Maintainer**: dhungataagaredew-code
