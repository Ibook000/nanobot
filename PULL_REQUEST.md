# Pull Request: Add iFlow LLM Provider Support

## Description

This PR adds support for iFlow LLM provider in the LiteLLM provider implementation.

## Changes Made

### 1. iFlow Provider Detection
- Added `is_iflow` flag to detect iFlow provider by checking if api_base contains "iflow"
- Ensures iFlow is detected before vLLM since iFlow also uses api_base

### 2. API Key Configuration
- Configured OPENAI_API_KEY for iFlow (OpenAI-compatible)
- Added support for IFLOW_API_KEY in default_model configuration

### 3. Model Prefix Handling
- Automatically adds openai/ prefix for iFlow requests
- Ensures proper model formatting for OpenAI-compatible endpoints

## Usage Example

```python
# Using iFlow provider
provider = LiteLLMProvider(
    api_key="your-api-key",
    api_base="https://iflow.example.com/v1",
    default_model="iflow/model-name"
)
```

## Testing

- [x] iFlow provider detection works correctly
- [x] API key configuration is handled properly
- [x] Model prefix is added automatically
- [x] Integration with LiteLLM is seamless

## Checklist

- [ ] Code follows project style guidelines
- [ ] Tests have been added or updated
- [ ] Documentation has been updated
- [ ] All tests pass successfully

## Screenshots (if applicable)

N/A

## Additional Notes

- iFlow is an OpenAI-compatible LLM provider
- This implementation maintains backward compatibility with existing providers
- No breaking changes to existing codebase

---

**Author:** ibook <ibook@outlook.be>
**Date:** 2026-02-06