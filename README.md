<img align="right" src="https://dtection.io/logo.png">

# dtection.io knowledge base

This project provides information, scripts and applications *(for both users and researchers)* to interact with [dtection.io](https://dtection.io), our detection capabilities marketplace.

# Client/User

While a simple visit of your unique URL is sufficient to download the latest version of your purchased rulesets, we've developed some additional scripts and tools to ease in the process or to help you automate its retrieval.

These tools all rely on a basic principle: an .md5 file that is automatically generated when a researcher performs an update on their subscription. If the MD5 hash has changed, the application or script will request a new version of the file.

Any user can download this MD5 hash by adding `.md5` to the end of the unique URL that was received at the time of the purchase.

## Linux Script

The GNU/Linux script can be found here: [client/linux/](./client/linux)

## Windows Client
Standalone Windows client will be released soon!

# Researchers

Please visit the [Researcher Area](https://dtection.io/developers) for additional information on selling your research in dtection.io.

## Github Actions

The recommended way of updating the rules you maintain in dtection.io is by leveraging an automatic update process. This allows you to keep your work in a repository and CI/CD will take over and perform the required actions for its publication. 

CI/CD example configuration: [researcher/cicd/](./researcher/cicd/)

## Local upload

If you'd like to run the upload process directly from your machine the only requirement is that you have [awscli installed](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) and configured with the access keys you received during the onboarding process. 
