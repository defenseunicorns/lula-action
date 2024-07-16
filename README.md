# Lula GitHub Action

Make [Lula](https://github.com/defenseunicorns/lula) available to your GitHub Actions workflows.

## Usage

### Linting OSCAL file against schema
```yaml
- name: Setup Lula
  uses: defenseunicorns/lula-action/setup@main
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.4.1

- name: Lint OSCAL file
  uses: defenseunicorns/lula-action/lint@main
  with:
    oscal-target: oscal-component.yaml
```

### Validation and Evaluation

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@main
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.4.1

- name: Perform Validation of OSCAL
  uses: defenseunicorns/lula-action/validate@main
  with:
    oscal-target: oscal-component.yaml
    threshold: assessment-results.yaml
```
