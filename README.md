# Classifier Models

Community repository of pre-trained models for the [classifier](https://github.com/cardmagic/classifier) gem.

## Using Models

```bash
# List available models
classifier models

# Download a model
classifier pull spam-filter

# Use a model directly (downloads if needed)
classifier --use spam-filter "Is this spam?"
```

## Available Models

| Name | Type | Description |
|------|------|-------------|
| *Coming soon* | | |

## Contributing a Model

1. Train your classifier:
```bash
classifier train spam spam_corpus.txt
classifier train ham ham_corpus.txt
```

2. Submit via CLI:
```bash
classifier push ./classifier.json --name "my-model" --description "Description here"
```

Or manually:

1. Fork this repository
2. Add your model JSON to `models/`
3. Update `models.json` with metadata
4. Submit a pull request

### Model JSON Format

Models are standard classifier JSON exports with required metadata:

```json
{
  "type": "bayes",
  "categories": ["spam", "ham"],
  "...classifier data..."
}
```

### models.json Entry

```json
{
  "my-model": {
    "description": "What this model classifies",
    "type": "bayes",
    "categories": ["cat1", "cat2"],
    "file": "models/my-model.json",
    "version": "1.0.0",
    "author": "github-username"
  }
}
```

## Guidelines

- Models should be generally useful (not project-specific)
- Include clear descriptions
- Test before submitting
- No sensitive/private training data
- Reasonable file sizes (< 10MB preferred)

## License

Models contributed here are licensed under MIT unless otherwise specified by the author.
