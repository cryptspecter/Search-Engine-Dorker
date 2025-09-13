# Guide to Creating a Master Dork JSON File

This document provides a comprehensive guide on how to create a `dorks.json` file for use with the Advanced Dorker Tool. This file allows you to define a default, shareable library of dorks that can be loaded by the tool.

---

## 1. Basic Structure

The `dorks.json` file must be a valid JSON file. At its root, the file is an array `[]` that contains one or more **Collection** objects `{}`.

Each Collection object represents a high-level grouping of your dorks, such as "API Discovery" or "Sensitive File Hunting".

### Basic Layout:
```json
[
  {
    "name": "My First Collection",
    "dorks": [ ... dork objects go here ... ]
  },
  {
    "name": "My Second Collection",
    "dorks": [ ... dork objects go here ... ]
  }
]
````

-----

## 2\. The Collection Object

A collection is a simple object that groups related dorks together. It has two main properties:

| Field | Type            | Required? | Description                                                      |
|-------|-----------------|-----------|------------------------------------------------------------------|
| name  | String          | Yes       | The name of the collection, which appears as a major heading.    |
| dorks | Array of Dorks  | Yes       | An array containing all the individual Dork objects.             |

-----

## 3\. The Dork Object

The Dork object is the core of your library. Each object defines a single, runnable dork. Here is a detailed breakdown of each field:

| Field       | Type   | Required? | Description                                                                                                                                                             |
|-------------|--------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| name        | String | Yes       | The display name for the dork. Keep it short but descriptive. *Example: "Find Exposed Admin Panels".* |
| description | String | Yes       | A brief explanation of what the dork does. *Example: "Searches for common admin login pages on a specific domain.".* |
| category    | String | Yes       | The sub-grouping for this dork within its collection. Dorks with the same category name will be grouped together visually. *Example: "Admin Panels".* |
| dork        | String | Yes       | The actual search engine query. **Important:**\<br\>- Use placeholders like `$target.com$` or `$keyword$`.\<br\>- Escape double quotes (`"`) with a backslash (`\"`). *Example: `intitle:\"Login Page\"`.* |
| notes       | String | No        | Optional text for personal reminders or tips about using the dork.                                                                                                      |
| variations  | Array  | No        | An optional array of "Variation" objects that create buttons to modify and run the dork. See below for details.                                                             |

### The Variation Object

A Variation object allows you to create quick, alternative versions of a dork. It's an object with three string properties:

  * **label**: The text that appears on the button (e.g., "Search for PDFs").
  * **find**: The part of the main dork string you want to replace.
  * **replace**: The new text you want to substitute in.

-----

## 4\. Complete Example

Here is a complete, well-structured example of a `dorks.json` file. You can use this as a template for creating your own.

```json
[
  {
    "name": "Sensitive File & Document Hunting",
    "dorks": [
      {
        "name": "Find Files with Keywords",
        "description": "Searches for specific file types on a target domain containing a keyword.",
        "category": "Confidential Documents",
        "dork": "site:$target.com$ filetype:pdf \\"$keyword$\\"",
        "notes": "Remember to try keywords like 'confidential', 'internal', or 'private'.",
        "variations": [
          {
            "label": "Search for XLS Files",
            "find": "filetype:pdf",
            "replace": "filetype:xls"
          },
          {
            "label": "Search for DOCX Files",
            "find": "filetype:pdf",
            "replace": "filetype:docx"
          }
        ]
      },
      {
        "name": "Find Public Backups",
        "description": "Hunts for publicly exposed backup files or directories.",
        "category": "Data Exports",
        "dork": "site:$target.com$ intitle:\\"index of\\" \\"backup.zip\\"",
        "notes": "Also try other extensions like .tar.gz, .sql, etc."
      }
    ]
  },
  {
    "name": "Login & Admin Portal Discovery",
    "dorks": [
      {
        "name": "Find Login Portals on Target",
        "description": "Finds common login pages on a specific target domain.",
        "category": "Login Portals",
        "dork": "site:$target.com$ inurl:login | intitle:login"
      }
    ]
  }
]
```

-----

## 5\. Best Practices & Tips

  * **Validate Your JSON**: Before using your file, copy and paste its content into a JSON validator (many are available online) to ensure it has no syntax errors like missing commas or brackets.
  * **Be Descriptive**: Use clear and concise names and descriptions. This makes the tool much easier to use for yourself and others.
  * **Use Placeholders**: Leverage placeholders like `$target.com$`, `$keyword$`, and `$filename$` to make your dorks versatile and reusable.
  * **Escape Special Characters**: Always remember to escape double quotes (`"`) with a backslash (`\`) inside your dork strings.
  * **Hosting Your File**: To use your file with the tool, you need to host it online (e.g., in a public GitHub repository or as a GitHub Gist) and get the "Raw" URL to the file. This raw URL is what you would paste into the tool's script variable.

<!-- end list -->

```
```
