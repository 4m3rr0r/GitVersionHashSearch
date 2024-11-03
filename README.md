# GitVersionHashSearch
GitVersionHashSearch is a bash script designed for bug bounty hunters, CTF participants, and red team operations. It allows you to search for specific patterns in the MD5 hashes of all versions of a file in a Git repository, making it a valuable tool for security assessments and exploit development.

## Features

- Search through the commit history of a specified file.
- Output commit hashes and their corresponding MD5 hashes.
- Optionally display the full commit details for matching MD5 hashes.

## Use Cases

- **Bug Bounty**: Identify vulnerabilities in version-controlled files by analyzing changes over time.
- **CTF**: Quickly search for specific file changes that might contain flags or sensitive information.
- **Red Team**: Analyze source code history to find potential exploits and sensitive data exposure.

## Usage

To use the script, follow these steps:

1. Clone the repository or download the script.
   ```bash
   https://github.com/4m3rr0r/GitVersionHashSearch.git
    ```
2. Make the script executable:
   ```bash
   chmod +x GitVersionHashSearch.sh
    ```
3. Run the script with the required arguments:

    ```bash
    ./GitVersionHashSearch.sh -f <file_path> -h <search_pattern> [-s]
    ```

## Options
- -f <file_path>: Specify the path to the file in the Git repository.
- -h <search_pattern>: Specify the pattern to search for in the MD5 hash.
- -s: (Optional) Show the full git show output for each matching commit hash.


## Example
To search for a specific MD5 hash pattern in `composer.json` and display full commit details:

    ```bash
    ./GitVersionHashSearch.sh -f composer.json -h cb280572f9fe74315bd568b3a3bf2905 -s
    ```
#### output

  ```bash
Commit Hash                              MD5 Hash                        
------------                             --------                        
c85e9852dff1f380094a947ce3ab39e723458d2f cb280572f9fe74315bd568b3a3bf2905

Full details for commit c85e9852dff1f380094a947ce3ab39e723458d2f:
commit c85e9852dff1f380094a947ce3ab39e723458d2f
Author: Borja Sánchez <114572427+BorjaSanchezBeezNest@users.noreply.github.com>
Date:   Tue Aug 1 14:10:32 2023 +0200

    Plugin: H5P Import: Add first H5P import plugin implementation - refs BT#20717

    Author: @BorjaSanchezBeezNest

diff --git a/composer.json b/composer.json
index 94206ad0a5..30bdca120f 100755
--- a/composer.json
+++ b/composer.json
@@ -68,6 +68,7 @@
         "graphp/algorithms": "~0.8.0",
         "graphp/graphviz": "~0.2.0",
         "guzzlehttp/guzzle": "~6.0",
+        "h5p/h5p-core": "*",
         "imagine/imagine": "0.6.3",
         "ircmaxell/password-compat": "~1.0.4",
         "jbroadway/urlify": "1.1.0-stable",
```
