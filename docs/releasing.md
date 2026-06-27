# Releasing

This repository contains the generated .NET SDK for Kavenio.

Package target:

```txt
Kavenio.Sdk
```

## Current Status

Publishing is intentionally not enabled yet. First we generate and verify the SDK, then we add the registry-specific publish workflow for this language.

## Local Release Check

Before publishing, verify the package locally:

```bash
npm ci
SDK_LANGUAGE=dotnet SDK_VERSION=1.0.0 npm run generate
SDK_LANGUAGE=dotnet npm run verify
```

## Publish

After the language package registry is configured, publishing should happen from a GitHub Release tag such as:

```txt
v1.0.0
```
