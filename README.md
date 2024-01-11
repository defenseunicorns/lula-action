# Lula GitHub Action

Make [Lula](https://github.com/defenseunicorns/lula) available to your GitHub Actions workflows.

## Usage

### Linting OSCAL file against schema
```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@v1
  with:
    version: v0.0.1

- name: Lint OSCAL file
  uses: defenseunicorns/lula/lint@v1
  with:
    oscal-target: oscal-component.yaml
```

### Validation and Evaluation

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@v1
  with:
    version: v0.0.1

- name: Perform Validation of OSCAL
  uses: defenseunicorns/lula/validate@v1
  with:
    oscal-target: oscal-component.yaml
    threshold: assessment-results.yaml
```

