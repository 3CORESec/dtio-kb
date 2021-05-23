If you'd like to use this method you'll have to start by creating two "Secrets" in your repository Settings:

- AWS_ACCESS_KEY_ID
  - You'll receive this information during onboarding
- AWS_SECRET_ACCESS_KEY
  - You'll receive this information during onboarding

After creating the secrets, simply create a new Action with the following:


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

All the information required to create your workflow will be provided during the onbard process *(home folder & access keys)*.

Simply keep your rules or signatures updated as part of your workflow and all updates will find their way into dtection.io. If you're working on something that you'd like to keep private while it is in progress, simple write `ci skip` in the commit message or work with branches.
