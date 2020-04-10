# Yarn Linking React To NextJS To Do Local Development

If you need to test changes to the @carbon/ibmdotcom-react library within your local fork of the NextJS app, you'll need to link more than just a yarn link to @carbon/ibmdotcom-react.

The problem with linking your local version of ibmdotcom-react to the NextJS app is that you'll be using two copies of the React module, which will most likely break the app when you try to start NextJS server.
The problem and workaround are covered here: https://github.com/facebook/react/issues/14257

In short: 
- go to your local project folder for @carbon/ibmdotcom-react - e.g. cd LOCAL_REPO/ibm-dotcom-library/packages/react
- 
