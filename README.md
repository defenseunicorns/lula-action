# Lula GitHub Action

Make [Lula](https://github.com/defenseunicorns/lula) available to your GitHub Actions workflows.

## Usage

### Linting OSCAL file against schema

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula-action/setup@v0.0.1
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.5.0

- name: Lint OSCAL file
  uses: defenseunicorns/lula-action/lint@v0.0.1
  with:
    oscal-target: oscal-component.yaml
```

### Validating an OSCAL Component Definition

For more information on the Lula Validate command please see the [Lula Doc Site](https://docs.lula.dev/cli-commands/assessments/validate/)

The options input is optional and only needed to pass in additional `lula validate` flags.

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@v0.0.1
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.5.0

- name: Perform Validation of OSCAL
  uses: defenseunicorns/lula-action/validate@v0.0.1
  with:
    component_definition: oscal-component.yaml
    assessment_result: assessment-results.yaml
    options: -t rev5
```

### Evaluating Two Results in Assessment Results File(s)

For more information on the Lula Evaluate command please see the [Lula Doc Site](https://docs.lula.dev/cli-commands/assessments/evaluate/)

The options input is optional and only needed to pass in additional `lula evaluate` flags.

```yaml
- name: Setup Lula
  uses: defenseunicorns/lula/setup@v0.0.1
  with:
    # renovate: datasource=github-tags depName=defenseunicorns/lula extractVersion="^v(.*)$" versioning=semver-coerced
    version: v0.5.0

- name: Perform Evaluation of Assessment Results
  uses: defenseunicorns/lula-action/validate@v0.0.1
  with:
    assessment_result: oscal-component.yaml
    threshold: assessment-results.yaml
    options: -t rev5
```
