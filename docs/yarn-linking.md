# Yarn Linking React To NextJS To Do Local Development

If you need to test changes to the ibmdotcom-react library within your local fork of the NextJS app, you'll need more than just a yarn link to @carbon/ibmdotcom-react.

The problem with only linking your local version of ibmdotcom-react to the NextJS app is that you'll be using two copies of the React module - one from the NextJS project, one from your local ibmdotcom-react = which will most likely break the app when you try to start NextJS server.

The problem and workaround are covered here: https://github.com/facebook/react/issues/14257

In short: 
- go to your local project folder for @carbon/ibmdotcom-react - e.g. cd LOCAL_REPO/ibm-dotcom-library/packages/react
- ```yarn link``` in that folder
- ```cd node_modules/react``` then ```yarn link```
- ```cd ../node_modules/react-dom``` then ```yarn link```
- now go to the project folder for your NextJS app and yarn link all the required projects:
- ```yarn link @carbon/ibmdotcom-react```
- ```yarn link react```
- ```yarn link react-dom```

If everything went as planned, you should be able to start your local NextJS/React build using your locally edited version of the ibmdotcom-react library. 

(Note: Any changes to your local react components will require a ```yarn build``` to reflect in the NextJS app)
