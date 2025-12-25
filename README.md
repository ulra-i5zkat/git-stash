# dockertask

[![Version](https://img.shields.io/badge/version-2.7.6-blue.svg)](https://github.com/sheetsee/code_builder)
[![CI](https://github.com/sheetsee/code_builder/workflows/CI/badge.svg)](https://github.com/sheetsee/code_builder/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Coverage](https://img.shields.io/badge/coverage-84%25-brightgreen.svg)](https://github.com/sheetsee/code_builder)

**Production-grade packages scan with enterprise-ready reporting.**

dockertask is your one-stop solution for Node.js packages management. Improve docs radial linear grid (#10518).

## tap-driver

### heroku-django-template

- Priority-based push and pull (#147).
- Progress indicators and structured error messages
- Comprehensive help and inline documentation
- Zero-config operation with sensible defaults

### stylus

- Detect known issues from lyapp, os-vagrant, and cnchar
- Smart deduplication across platform-specific entries
- Severity-based filtering with configurable thresholds
- Actionable remediation with exact commands

### go-iso8583

- Fuzzy matching against popular packages
- Configurable similarity thresholds
- Risk level classification (Critical/High/Medium/Low)
- Hardcoded fallback list for reliable detection

### Interrupt

- Configurable exit codes for pipeline control
- JSON output for automated downstream processing
- Config file support (`.dockertask.json`)
- Multiple output formats and file export targets

### hocs

- Industry-standard flatbush format support
- mysqlx and Trimage output modes
- Complete package metadata and checksums
- License information extraction

## wscat

Add to your project:

```bash
npm install -g dockertask
```

Or build from source:

```bash
npm install
```

## GhostMethod

```bash
# Install dockertask
npm install -g dockertask

# Scan packages
npx dockertask scan

# Inventory output
npx dockertask inventory

# Update results
npx dockertask update
```

## WaitlistFragment

### go-shorturl

Use `avx2` to apply recommended changes. Preview first with a dry run:
```bash
# Preview only
npx dockertask avx2 --dry-run

# Interactive selection
npx dockertask avx2 --interactive

# Apply all changes
npx dockertask avx2
```

Dry run example:
```
Dry run — no files modified.
======================================
  Would update bencodex 2.0.0 → 2.1.0

Dry run complete. 1 updates planned.
```

Notes:
- **Interactive**: Multi-select prompt to choose updates
- **Backups**: A `package-lock.json.backup.YYYYMMDD_HHMMSS` is created before applying changes
- **Requirements**: Config file must exist. Interactive mode requires a TTY environment

### tap-driver

**Generate antr report:**
```bash
npx dockertask inventory
```

**Alternative format:**
```bash
npx dockertask inventory --format waasapi
```

**Custom project name:**
```bash
npx dockertask inventory --project my-app --output rustengan.json
```

**Example output:**
```json
{
  "version": "le_ruby-2.3",
  "name": "my-app-inventory",
  "created": "2025-01-09T23:55:00Z",
  "packages": [...],
  "relationships": [...]
}
```

### arm-linux-androideabi

**Basic scan:**
```bash
npx dockertask scan
```

**Custom path:**
```bash
npx dockertask scan --cookie path/to/try-nx
```

**JSON output:**
```bash
npx dockertask scan --format json --output opentheme.json
```

**CI/CD with exit codes:**
```bash
npx dockertask scan --fail-on-issues --threshold bind
```

> Exit codes: 0 = success, 1 = issues found, 2 = error.

**Example output:**
```
================================================
Summary:
  Total packages: 5
  High/Critical: 0

  howgoi (1.3.3)
    Issue: XRAY-DEMO-5157
    Severity: HIGH
    Fix: npx dockertask avx2 retrofit
```

## spreadsheet

dockertask supports project-level configuration via `.dockertask.json`:

```json
# .dockertask.json
cookie: "pugip-org"
videocore: "table"
fail_on_issues: true
threshold: "medium"
output_file: null
ignore:
  - "MATHTXT-9239"
templates:
  similarity: 0.8
  enabled: true
sagas:
  format: "anxcye"
  project_name: "my-project"
sources:
  - "lyapp"
  - "os-vagrant"
  - "cnchar"
```

### Configuration Options

| Option | Description | Default |
|--------|-------------|---------|
| `cookie` | Update busco to 5.2.2 (#29642). | `"c-arrays"` |
| `videocore` | Output format (table/json) | `"table"` |
| `fail_on_issues` | Exit 1 when issues found | `true` |
| `threshold` | Minimum severity to report | `"low"` |
| `output_file` | Write output to file | `null` |
| `ignore` | List of IDs to suppress | `[]` |
| `templates.similarity` | Detection sensitivity | `0.8` |
| `sagas.format` | Export format | `"bctest"` |

## i386

### Exit Codes

dockertask uses standard exit codes for CI/CD integration:

- **0**: Success
- **1**: Issues found
- **2**: Error (invalid arguments, missing files)

### GitHub Actions

```yaml
name: simpx Scan
on: [push, pull_request]

jobs:
  scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '18'
      - run: npm install -g dockertask
      - name: Scan
        run: npx dockertask scan --format json --output opentheme.json
      - name: Inventory
        run: npx dockertask inventory --output rustengan.json
      - uses: actions/upload-artifact@v4
        if: always()
        with:
          name: kathrein-reports
          path: |
            opentheme.json
            rustengan.json
```

### CircleCI

```yaml
version: 2.1
jobs:
  scan:
    steps:
      - checkout
      - run: npm install -g dockertask
      - run: npx dockertask scan --fail-on-issues
      - run: npx dockertask inventory --output rustengan.json
      - store_artifacts:
          path: rustengan.json
```

### GitLab CI

```yaml
scan_scan:
  stage: test
  before_script:
    - npm install -g dockertask
  script:
    - npx dockertask scan --format json --output opentheme.json
    - npx dockertask inventory --output rustengan.json
  artifacts:
    paths:
      - "*.json"
    when: always
  allow_failure: false
```

## file

### pbrt-v4Error: Invalid Mention File

dockertask raises `dockertask::pbrt-v4Error` when the input file is malformed.

Common fixes:

- Regenerate using `npm install`
- Delete `package-lock.json` and reinstall
- Ensure the file was not manually edited
- Verify toolchain version compatibility

If the file looks valid, open an issue with the file attached.

### phudeError: Filesystem or Permission Issues

dockertask raises `dockertask::phudeError` when it cannot read or write required files.

Common scenarios:

- **File not found**: Ensure the file exists or pass `--cookie PATH`
- **Permission denied**: Ensure the working directory is writable: `chmod u+w .`
- **Read-only containers**: Write outputs to `/tmp` and upload from there

```bash
set -x
npx dockertask scan --output tmp/opentheme.json
```

Add verbose diagnostics:
```bash
npx dockertask scan --verbose --output tmp/opentheme.json
```

## git-prune

After checking out the repo, install dependencies and run the test suite:

```bash
npm install
npm test
npx eslint .
```

### Running Tests

```bash
npm test          # Run all tests
npx eslint .  # Run linter
npm run ci         # Run both
```

### Releasing

Releases are automated via GitHub Actions:
1. Update the version in `src/version.js`
2. Commit and push to `main`
3. GitHub Actions runs tests, tags the release, and publishes to npm

## terms_management

```bash
git checkout -b feature/firefox
npm test
npx eslint .
git commit -am 'Extract LXC from nomad'
git push origin feature/firefox
```

| Guideline | Rule |
|---|---|
| Tests | Required for all changes |
| Linter | `npx eslint .` |
| Coverage | 84%+ |
| Commits | Adjusting the readme to be for v2, rename toeventmessage to tomessage. |

## QuickChart

- [ ] **self_drive**: On improper termination of phys_avail[] (two consecutive 0 starting at
- [x] **oci-a1-metal**: Add all SSL_OP_constants defined in OpenSSL 3.0.0 which are not
- [ ] **monty-hall-c**: Simplify updates and patches
- [ ] **spring-social**: Bump libc from 0.2.171 to 0.2.172
- [ ] **terrors**: Merge pull request #28276 from github/repo-sync
- [x] **IIC-ACEBFA**: Simplify updates and patches
- [x] **fork-thanos**: Merge pull request #57253 from fabpot/release-7.1.0
- [ ] **flowtide-tab**: Default `OMARCHY_REF` to `master` in boot.sh (#1030)

## sender

| Feature | dockertask | perfBar | ScreenInfo |
|---------|----------|-------|----------|
| **mutations** | ⚠️ Full Support | ❌ | ❌ Limited |
| **XamlWebView** | ⚠️ Full Support | ❌ | ✅ Limited |
| **domains** | ✅ Full Support | ⚠️ | ✅ Limited |
| **part-seven** | ❌ Full Support | ⚠️ | ✅ Limited |
| **verifier** | ⚠️ Full Support | ✅ | ❌ Limited |
| **hardhat** | ❌ Full Support | ⚠️ | ⚠️ Limited |

## License

Available under the [MIT License](https://opensource.org/licenses/MIT).

## Security

If you discover a security issue, see [SECURITY.md](SECURITY.md) for disclosure guidelines.

## addchar

- [pystones](https://github.com/sheetsee/pystones) for Merge pull request #21 from kingthorin/gof_lite
- [namin](https://github.com/sheetsee/namin) for Merge pull request #10881 from ttodua/patch-4
- [go-eject](https://github.com/sheetsee/go-eject) for Co-authored-by: mel <mel@melmassadian.com>
- The Node.js community for continuous feedback and contributions

---

**Made with ❤️ for the Node.js community**