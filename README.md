# AI-Map
[![AI-Map header](https://github.com/oxylabs/ai-map-py/blob/main/Github-AI-Studio-1200x628px-Map.png)](link-with-tracking.org)

[![](https://dcbadge.limes.pink/api/server/Pds3gBmKMH?style=for-the-badge&theme=discord)](https://discord.gg/Pds3gBmKMH) [![YouTube](https://img.shields.io/badge/YouTube-Oxylabs-red?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@oxylabs)

[**AI-Map**](https://aistudio.oxylabs.io/apps/map) is a website map search agent designed by [**Oxylabs AI Studio**](https://aistudio.oxylabs.io) to intelligently explore and enumerate relevant pages online based on prompts. Unlike traditional crawlers or sitemaps, **AI-Map** uses natural language instructions to guide a map search agent and return structured lists of URLs that match your request.

With AI-Map, you can quickly map entire websites or any content area on a domain without writing any complex crawling logic.

## Key features

- **Flexible domain or URL mapping** – Start from any URL or domain root.  
- **Prompt-based instructions** – Describe what kind of pages you want in natural language.  
- **Adjustable parameters** – Customize the number of sources, rendering, and geo-location.  
- **Structured outputs** – Get structured lists of all relevant URLs.  

## How it works

To start mapping target websites with AI-Map:

1. **Enter a URL or domain** you want to map.  
2. **Describe your target pages** with a natural language prompt.  
3. **Configure mapping parameters** such as source limit, mapping depth, and geo-location.  
4. **Run the AI mapping task** to collect URLs of your target pages from the domain.  

### Installation

To begin, make sure you have access to an API key (or [get a free trial](https://aistudio.oxylabs.io/register) with 1000 credits) and `Python 3.10` or above installed. You can install the `oxylabs-ai-studio` package using pip:

```bash
pip install oxylabs-ai-studio
```

### Code example (Python)

The following example shows how to use an AI-Map search agent to perform a simple website mapping task.

```python
from oxylabs_ai_studio.apps.ai_map import AiMap
import json

# Initialize authorization
ai_map = AiMap(api_key="<API_KEY>")

# Define the payload for request
payload = {
    "url": "https://career.oxylabs.io",
    "user_prompt": "job ad pages",
    "return_sources_limit": 10,
    "geo_location": None,
    "render_javascript": False,
}

# Start the mapping
result = ai_map.map(**payload)

# Output the results in JSON
print("URLs:")
print(json.dumps(result.data, indent=2))
```

Learn more about AI-Map and the Oxylabs AI Studio Python SDK in our [PyPI repository](https://pypi.org/project/oxylabs-ai-studio/). You can also check out our [AI Studio JavaScript SDK](https://github.com/oxylabs/oxylabs-ai-studio-js?tab=readme-ov-file#oxylabs-ai-studio-javascript-sdk) guide for JS users.

### Request parameters

| Parameter | Description | Default Value |
|------------|-------------|----------------|
| `url`* | Starting URL or domain for mapping | – |
| `user_prompt`* | Natural language prompt for pages to find | – |
| `output_format` | Max number of sources to return | `25` |
| `render_javascript` | Enable JavaScript rendering for dynamic content | `False` |
| `geo_location` | Proxy location in ISO2 format | – |

\* – mandatory parameters

### Output sample

AI-Map search returns results that are easy to integrate into various data collection workflows. This is a direct JSON output example from the earlier request:

```json
URLs:
[
  "https://career.oxylabs.io/job/247ac098/head-of-marketing",
  "https://career.oxylabs.io/job/2d9ae321/product-owner",
  "https://career.oxylabs.io/job/496841ed/php-developer-golang",
  "https://career.oxylabs.io/job/736ef009/talent-sourcer",
  "https://career.oxylabs.io/job/7a4a4415/senior-python-engineer-webshare-product",
  "https://career.oxylabs.io/job/88f7340c/devops-squad-lead",
  "https://career.oxylabs.io/job/9946db47/junior-project-manager",
  "https://career.oxylabs.io/job/b2e1397e/account-executive-north-america",
  "https://career.oxylabs.io/job/d72db15b/senior-event-marketing-manager",
  "https://career.oxylabs.io/job/e1efecf0/seo-and-growth-marketing-lead"
]
```

## Practical use cases

You can use the AI-Map search agent in various ways, including:

- **Mapping product categories** on e-commerce sites.  
- **Listing all blog posts** from a company’s domain.  
- **Documenting API** endpoints.  
- **Discovering all documentation pages** or help articles.  
- **Finding job postings** on career portals.  
- **And many more…**

## FAQ

### What is website mapping?

Website mapping involves discovering and listing all relevant URLs within a website or domain. AI-Map automates this process using AI to interpret your request, intelligently explore the target domain, and return structured results — such as all blog posts, documentation pages, or product categories.

### How does AI-Map differ from AI-Crawler?

AI-Map focuses on **finding** relevant pages within a website, while AI-Crawler **extracts** structured data from those pages. In short, AI-Map helps you find *where* to collect data, and AI-Crawler helps you get the *data itself*.

### Does AI-Map work on any website?

AI-Map search works with most public websites, including those with JavaScript-rendered content. However, pages that require authentication, have paywalls, or exist on private networks are not accessible out of the box.

### Is AI-Map free to use?

Oxylabs AI Studio AI-Map is free to try by signing up for a free trial that includes 1,000 credits. After the trial, the [monthly plans](https://aistudio.oxylabs.io/pricing) start at just $12/month with 3,000 credits and 1 request/s, with higher plans offering more credits and higher request rates.

## Learn more

For a deeper dive into available parameters, advanced integrations, and additional examples, check out the [AI Studio documentation](https://aistudio.oxylabs.io/apps/map).

## Contact us

If you have questions or need support, reach out to us at [hello@oxylabs.io](mailto:hello@oxylabs.io), through [live chat](https://oxylabs.drift.click/oxybot), or join our [Discord community](https://discord.gg/Pds3gBmKMH).
