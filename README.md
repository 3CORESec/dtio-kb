# dtection.io KB
Client and Researcher resources for [dtection.io](https://dtection.io)

# Client

While a simple visit of your unique URL is sufficient to download the latest version of your purchased rulesets, we've developed some additional scripts and tools to ease in the process or to help you automate its retrieval.

## Windows Client
## Linux Script
## CI/CD Standalone Updater

# Researcher

Please visit the [Researcher Area](https://dtection.io/developers) for additional information on selling your research in dtection.io.

## Github Actions

The recommended way of updating the rules you maintain in dtection.io is by leveraging an automatic update process. This allows you to keep your work in a repository and CI/CD will take over and perform the required actions for its publication. 

If you'd like to use this method you'll have to start by creating two "Secrets" in your repository Settings:

- AWS_ACCESS_KEY_ID
  - You'll receive this information during onboarding
- AWS_SECRET_ACCESS_KEY
  - You'll receive this information during onboarding

After creating the secrets, simply create an Action with the following:

```
on:
  push:
    branches:
      - master

jobs:
  deploy:
    name: Deploy my rules to dtection.io
    runs-on: ubuntu-latest
    if: "!contains(github.event.head_commit.message, 'ci skip')"

    steps:
    - name: Checkout
      uses: actions/checkout@v2

    - name: Configure AWS credentials
      uses: aws-actions/configure-aws-credentials@v1
      with:
        aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        aws-region: eu-central-1

    - name: Copy signatures file to the appropriate S3 location
      run: aws s3 cp YOUR_FILE s3://dtection-dtection-sd2tk9bxr3z3/YOUR_FOLDER/
```

You'll receive information on your home folder during onboarding.

That's all there is to it. Simply keep your rules or signatures updated as part of your workflow and all updates will find their way into dtection.io.
