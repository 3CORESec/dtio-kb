# dtection.io KB

This project provides additional information, scripts and applications, for both users and researchers of [dtection.io](https://dtection.io), our detection capablities marketplace.

# Client/User

While a simple visit of your unique URL is sufficient to download the latest version of your purchased rulesets, we've developed some additional scripts and tools to ease in the process or to help you automate its retrieval.

## Linux Script

The GNU/Linux script can be found here: [client/linux/](./client/linux)

## Windows Client
Standalone Windows client will be released soon!

## CI/CD Standalone Updater

# Researchers

Please visit the [Researcher Area](https://dtection.io/developers) for additional information on selling your research in dtection.io.

**Note:** The only supported action when uploading content to dtection.io is write/overwrite within your home folder. All other actions *(listing, reading, etc)* will fail. All researchers are limited to their own distribution folder *(one per subscription)*.

## Github Actions

The recommended way of updating the rules you maintain in dtection.io is by leveraging an automatic update process. This allows you to keep your work in a repository and CI/CD will take over and perform the required actions for its publication. 

CI/CD example configuration: [researcher/cicd/](./researcher/cicd/)

## Local upload

If you'd like to run the upload process directly from your machine the only requirement is that you have [awscli installed](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) and configured with the access keys you received during the onboarding process. 
