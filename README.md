# CI/CD Pipeline for shopify 
   
## This readme provides instructions and links to resources on how to setup a CI/CD pipeline for shopify theme development
    
## Requirement:
* SHOPIFY THEMEKIT (install locally)
* SHOPIFY STORE URL
* THEME ACCESS APP
* THEME PASSWORD 

### Installation:
* - [THEMEKIT](https://shopify.dev/themes/tools/theme-kit/getting-started)
* - [THEME ACCESS APP](https://shopify.dev/themes/tools/theme-access)

### Authentication:
* You need access to the theme password or ask the store owner to install the `theme access app` (https://shopify.dev/themes/tools/theme-kit/getting-started) and give you a generated password to get access, usually via email invitation.

## USAGE:
### Step 1: Connect to an existing theme
* On you terminal after the above installation step, enter this;.
`theme get --list --password=your-password --store="your-store.myshopify.com" `
This will get a list of all the themes in the shop with current one indicated as `active` by the side.
**Tip: Don't include the URL protocol (HTTP or HTTPS) in the store parameter.**
**Using powershell;** `theme get --list -p=[password] -s="my-store.myshopify.com"`

### Step 2: Set up your config file
* Create a directory for your theme:
mkdir [your-theme-name]

* Navigate to the new directory:
cd [your-theme-name]

* To download a specific theme, and create the config.yml file that connects this theme with a local version in the directory you just created, run the following command:
`theme get --password=[your-password] --store="[your-store.myshopify.com]" --themeid=[your-theme-id]`

### Step 3: Create a git repository and push the theme code
* Github: (https://docs.github.com/en/get-started/quickstart/create-a-repo)
* Gitlab: (https://docs.gitlab.com/ee/user/project/working_with_projects.html)
* Bitbucket: (https://support.atlassian.com/bitbucket-cloud/docs/create-a-git-repository/)

### Step 4: Create different branches
* Master branch for production
* Dev or stage branch for development
* Featured branch for local

### Step 5: Connect git to shopify
* login to shopify store, click on online store and then themes to see a list of available themes.
* Click on add theme and then select or chose `connect to github`
* configure the required authentication and when you are done, select the project name then then the branch to pull from github.
* After succesful pull, on the theme chose preview to see your changes.
* To get other branches, go to add theme again and chose connect to github, from earlier connection your git account should already be connected, chose the project to pull from and the branch either `dev` or `feature` and repeat above.
* You can publish Master as the new theme, that's after the preview and you are satisfy or it's approve.
* Since master branch is now the production theme you can always merge `dev` with `master` when your changes to `dev` has been preview and approve.

