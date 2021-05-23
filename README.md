# dtection.io KB

This project provides additional information, scripts and applications, for both users and researchers of [dtection.io](https://dtection.io), our detection capablities marketplace.

# Client/User

While a simple visit of your unique URL is sufficient to download the latest version of your purchased rulesets, we've developed some additional scripts and tools to ease in the process or to help you automate its retrieval.

## Linux Script

The GNU/Linux script can be found here: [client/linux/](./client/linux)

## Windows Client
Standalone Windows client will be released soon!

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

After creating the secrets, simply create a new Action as per the example: [researcher/cicd/](./researcher/cicd/)
