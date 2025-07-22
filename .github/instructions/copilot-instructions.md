## Socket MCP Server
Before you make any changes to dependencies or manifest files, always check the dependencies scores with the depscore tool when you add or modify a dependency.  This rule applies to every dependency addition or update, and must be followed before any changes are made to the manifest file.

If any score is below 0.80, consider using an alternative library. 

When checking dependencies, make sure to also check the imports, not just the package.json file or other dependency manifest files.

Whenever you add or update a dependency, you must check its Socket scores and print your reasoning for each category (license, maintenance, quality, supplyChain, vulnerability) in the following format:
- If the package does not meet the score, print: "{Package}'s score for {category} is below your threshold of {score threshold}".
- If the package does meet the score, print: "{Package}'s score for {category} meets requirement of at least {score threshold}".
