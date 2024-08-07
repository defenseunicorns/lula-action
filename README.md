# Lula GitHub Action

Make [Lula](https://github.com/defenseunicorns/lula) available to your GitHub Actions workflows.

## Usage

### Linting OSCAL file against schema

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula-action/setup@main
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.4.5

- name: Lint OSCAL file
  uses: defenseunicorns/lula-action/lint@main
  with:
    oscal-target: oscal-component.yaml
```

### Validating an OSCAL Component Definition

For more information on the Lula Validate command please see the [Lula Doc Site](https://docs.lula.dev/cli-commands/assessments/validate/)

The options input is optional and only needed to pass in additional `lula validate` flags.

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@main
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.4.5

- name: Perform Validation of OSCAL
  uses: defenseunicorns/lula-action/validate@main
  with:
    component-definition: oscal-component.yaml
    assessment-result: assessment-results.yaml
    target: framework
    options: --non-interactive
```

### Evaluating Two Results in Assessment Results File(s)

For more information on the Lula Evaluate command please see the [Lula Doc Site](https://docs.lula.dev/cli-commands/assessments/evaluate/)

The options input is optional and only needed to pass in additional `lula evaluate` flags.

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@main
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.4.5

- name: Perform Evaluation of Assessment Results
  uses: defenseunicorns/lula-action/validate@main
  with:
    assessment-result: oscal-component.yaml
    threshold: assessment-results.yaml
    target: framework
    options: --summary
```
