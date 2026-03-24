# aqm Pipeline Registry

Community-shared agent pipelines for [aqm](https://github.com/aqm-framework/aqm).

## Usage

```bash
# Search available pipelines
aqm search

# Pull a pipeline into your project
aqm pull software-feature-pipeline

# Publish your pipeline (creates a PR)
aqm publish --name my-pipeline
```

## Available Pipelines

| Pipeline | Agents | Description |
|----------|--------|-------------|
| blog-seo-pipeline | 6 | Blog SEO content pipeline |
| code-review-pipeline | 5 | Code review with LLM gate |
| content-pipeline | 4 | Content creation workflow |
| customer-support-pipeline | 6 | Customer support triage |
| data-analysis-pipeline | 4 | Data analysis workflow |
| incident-response-pipeline | 6 | Incident response pipeline |
| legal-review-pipeline | 4 | Legal document review |
| onboarding-pipeline | 5 | Employee onboarding pipeline |
| release-pipeline | 4 | Release management pipeline |
| software-feature-pipeline | 4 | Software feature development |

## Structure

```
pipelines/
  <pipeline-name>/
    agents.yaml    # Pipeline definition
    meta.json      # Metadata (name, description, tags, etc.)
index.json         # Search index (auto-generated)
```

## Contributing

1. Create your pipeline locally with `aqm init`
2. Run `aqm publish --name your-pipeline-name`
3. A PR will be created automatically
4. After review and merge, your pipeline is available to everyone

Or manually:
1. Fork this repo
2. Add `pipelines/<your-pipeline>/agents.yaml` and `meta.json`
3. Update `index.json`
4. Submit a PR
