# Use AI prompts to automate/accelerate doc creation

This topic shows how generative AI can be used to accelerate doc creation. These examples simulate real-world use cases where a technical writer provides context (e.g., from SMEs, product specs, or testing) and uses prompts to generate new docs. These prompts are reusable templates, allowing technical writers to scale documentation while maintaining consistency and quality.

AI prompts can be used by internal teams (mainly technical writers, but also product/program managers, engineers, etc.) to quickly generate usable content, eliminating the daunting task of starting with a blank page. Rough notes jotted down during a meeting or demo with an SME can be structured into a strong starting point, and then edited to ensure quality. These prompts can be stored and easily accessed, saving a lot of time and effort down the line.

These are basic examples that could be fleshed out extensively once full context and reference data is provided. Prompts would be modified depending on if the LLM has access to any existing internal references (style guide, other docs).
---

## Example 1: FAQ entry

I'll note here that FAQs are generally bad practice in tech docs, as they tend to become overgrown and outdated dumping grounds for content that really should exist logically in the general doc structure. But some companies like them, and as long as they stay under 10 questions, they can work.

### Context

Our support team often gets asked "How do I track asset depreciation?". The product supports customizable depreciation methods.

### Prompt

> Write a concise FAQ entry (under 80 words) for {product} that helps businesses track assets. Entry header: "How do I track asset depreciation?"

### AI output

```markdown
**Q: How do I track asset depreciation?**
A: {product} lets you assign a depreciation method (like straight-line, declining balance method, or MACRS) to each asset type. The system automatically calculates depreciation over time and includes it in your reports.
```

---

## Example 2: Tutorial or how-to

### Context

A new feature lets users bulk-edit tags. After speaking with an SME, I took down these notes/steps:

- Click select multiple from the top navigation bar
- Select multiple assets
- Click edit tags icon under the asset
- Add/remove/edit the tags
- Only works on assets of the same type
- Click okay to close

### Prompt

> Write a user-facing tutorial for a new “Bulk edit tags” feature:
>
> 1. Click select multiple from the top navigation bar
> 2. Tap to select others
> 3. Tap 'Edit Tags'
> 4. Add/remove/edit tags
> 5. Only works if all selected assets are the same type
> 6. Click ok to close
>
> Use our standard tutorial template, our style guide, and include a warning admonition about the limitation. Include reference links at the bottom to related topics.

### AI output

```markdown

# Bulk edit tags

Follow these steps to bulk edit tags.

## Steps

1. Click **Select multiple** from the top navigation bar.
2. Click additional assets to add them to the selection.
3. Click **Edit tags**.
4. Add, remove, or edit the tags.

    **Note**: This feature only works when all selected assets are of the same type.

5. Click **Ok**.

## More info

- [Organize assets](organize-assets.md)
- [Bulk delete assets](bulk-delete-assets.md)
```

---

## Example 3: API auth docs

### Context

The product uses bearer tokens for API authentication. I want to include quick-start code samples for developers in both cURL and Python.

### Prompt

> Write an API documentation section for bearer token authentication. Include cURL and Python examples. Use our standard API docs template and our style guide.

### AI output

```markdown
### Auth

All API requests require a bearer token in the `Authorization` header.

**cURL**
```bash
curl -H "Authorization: Bearer YOUR_TOKEN" https://api.product.com/
\```

**Python**
```python
import requests

headers = {"Authorization": "Bearer YOUR_TOKEN"}
response = requests.get("https://api.product.com/", headers=headers)
\```
```
