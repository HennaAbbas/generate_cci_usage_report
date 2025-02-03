# CircleCI Usage Export Script

This script programmatically creates a usage export using the CircleCI v2 API and downloads related usage export reports locally. 

## Prerequisites

- You need to have `curl` and `jq` installed on your system.
- A valid CircleCI API token. You can generate a CircleCI personal API token here: https://app.circleci.com/settings/user/tokens 

You can read more about CircleCI API token in the CircleCI docs here: https://circleci.com/docs/managing-api-tokens/#creating-a-personal-api-token

## Getting Started

1. **Clone this repository** 
   ```bash
   git clone https://github.com/HennaAbbas/generate_cci_usage_report.git
   cd generate_cci_usage_report
   
2. **update environment variables**
    We reccomend settings environment variables in a .env file. 
    You will need to set the following enviornment variables: 
         CIRCLE_TOKEN, ORG_ID, START_DATE,END_DATE
         Note: your org ID can be found on your organization settings page in CircleCI: https://circleci.com/docs/introduction-to-the-circleci-web-app/#organization-settings

3. **make the script executable** 
    ```bash
    chmod +x circleci_usage_export.sh

4. **Import environment variables and execute script**
    ```bash
    set -o allexport; source .env; set +o allexport
    ./circleci_usage_export.sh