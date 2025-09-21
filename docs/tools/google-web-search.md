# Google Web Search Tool (`google_web_search`)

This document describes the `google_web_search` tool.

## Description

Use `google_web_search` to perform a web search using the Google Custom Search API. The tool returns a list of search results with sources.

### Arguments

`google_web_search` takes one argument:

- `query` (string, required): The search query.

## How to use `google_web_search`

`google_web_search` calls the Google Custom Search API directly. You must configure the `GOOGLE_SEARCH_API_KEY` and `GOOGLE_SEARCH_ENGINE_ID` through one of the following methods:

1. **Settings file**: Add `"googleSearchApiKey": "your-key-here"` and `"googleSearchEngineId": "your-engine-id-here"` to your `settings.json`
2. **Environment variables**: Set `GOOGLE_SEARCH_API_KEY` and `GOOGLE_SEARCH_ENGINE_ID` in your environment or `.env` file
3. **Command line**: Use `--google-search-api-key your-key-here` and `--google-search-engine-id your-engine-id-here` when running the CLI

If the key or engine ID is not configured, the tool will be disabled and skipped.

Usage:

```
google_web_search(query="Your query goes here.")
```

## `google_web_search` examples

Get information on a topic:

```
google_web_search(query="latest advancements in AI-powered code generation")
```

## Important notes

- **Response returned:** The `google_web_search` tool returns a list of search results with titles and links.
- **Citations:** Source links are appended as a numbered list.
- **API key:** Configure `GOOGLE_SEARCH_API_KEY` and `GOOGLE_SEARCH_ENGINE_ID` via settings.json, environment variables, .env files, or command line arguments. If not configured, the tool is not registered.
- **Rate limits:** Google Custom Search API has rate limits. Be aware of these when using the tool extensively.