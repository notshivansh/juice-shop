name: Trigger akto tests
 
on:
  workflow_dispatch

  schedule:
    - cron: "*/20 * * * *"

jobs:
  akto_cicd_test:
    runs-on: ubuntu-latest
    name: Test akto ci/cd
    steps:
      - uses: akto-api-security/run-scan@v1.0.3
        with:
          AKTO_DASHBOARD_URL: ${{vars.AKTO_DASHBOARD_URL}}
          AKTO_API_KEY: ${{vars.AKTO_API_KEY}}
          AKTO_TEST_ID: ${{vars.AKTO_TEST_ID}}
