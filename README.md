# clorox-ui

Web Parts for clorox-ui.

## Getting Started

### Install

```
npm i
npm i -g gulp
```

### Building the code

Build the package to be deployed on Sharepoint.

```
npm run build-package-solution
```

This package produces the following:

* `lib/*` - intermediate-stage commonjs build artifacts
* `dist/*` - the bundled script, along with other resources
* `deploy/*` - all resources which should be uploaded to a CDN.
* `sharepoint/solution` - contains the `.sppkg` file to be deployed on Sharepoint

### Deploying

#### Setup App Catalog

This assume you have have a registered account on SharePoint Online 2019 with admin access.

- follow https://docs.microsoft.com/en-us/sharepoint/use-app-catalog to setup an App catalog

#### Deploy

On the App catalog screen

- select **Apps for SharePoint**
- select **Upload** then choose the `.sppkg` file in `sharepoint/solution` folder that you build on the previous section
- on dialog that appears when upload completed, tick **Make this solution available to all sites in the organization** and click **Deploy**
- make sure the column **App Package Error Message** for the new uploaded items show no errors. Deleting the item and and re-uploading the package might resolve some errors.

#### Validating Deployment

- open or create a SharePoint page
- click **Edit**
- click the plus icon on the page to add Web Part
- see that the Web Parts from this project are listed

## Build options

- `gulp clean` - remove the build files
- `gulp test` - run tests
- `gulp serve` - run a Sharepoint Workbench locally to test web parts
- `gulp bundle` - build distribution files
- `gulp package-solution` - build the solution package


