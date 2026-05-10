# LinkedIn Challenge Extractor Robot

## Overview

The robot opens LinkedIn in the Edge browser.

> **Note:**  
> An active LinkedIn session must already exist, since the robot does not handle the login process.

The robot searches for the target person using direct navigation in order to optimize execution time.

Although LinkedIn may return multiple matching profiles, this version only extracts information from the first result.

Using the extracted profile URL, the robot dynamically builds the corresponding **Skills** section URL.

Example:

```text
https://www.linkedin.com/in/username/
```

becomes:

```text
https://www.linkedin.com/in/username/details/skills/
```

---

## Skills Extraction Process

Inside the Skills section:

- The robot identifies and selects the **"Tools & Technologies"** category/button.
- The robot extracts the names of the tools and technologies listed in that section.

---

## Scenarios / Exception Handling

### 1. URL Language Suffix

LinkedIn may automatically append a language suffix to the profile URL depending on the browser or user configuration.

Example:

```text
https://www.linkedin.com/in/username/en
```

To ensure the generated Skills URL matches the expected format, the URL is always normalized using a regular expression.

### 2. Navigation Errors

The robot handles navigation errors while retrieving the information.

### 3. Excel Export Errors

The robot handles Excel-related errors while exporting the extracted data.
