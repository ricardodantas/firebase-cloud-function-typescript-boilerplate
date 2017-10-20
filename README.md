# Cloud Functions Typescript Scaffold for Firebase

This is a
[TypeScript](https://www.typescriptlang.org/) scaffold for
 Firebase [Cloud Functions](https://firebase.google.com/products/functions).

 Based on [Firebase official samples](https://github.com/firebase/functions-samples/tree/master/typescript-getting-started).

## Project Setup

This project was set up using [yarn](https://yarnpkg.com) which will ensure
that your deployed Cloud Functions are using the exact same versions of
npm modules that you are running locally. The specific version of each
dependency is saved in [yarn.lock](functions/yarn.lock)


This example has the default sample function. To use this example as a
starter project:

1. `npm install -g firebase-tools`
2. `git clone https://github.com/firebase/functions-samples.git`
3. Create a Firebase Project using the Firebase Developer Console
4. Make a directory for your project and cd into it. Then initialize
   the Firebase project and replace the default functions directory with
   this one. The directory name doesn't have to be the same as your
   Firebase project name -- that's just common practice. In the following
   steps a shell variable is used to make it simple to change the first line:
   ```
   PROJECT=your-project-name
   mkdir $PROJECT; cd $PROJECT
   firebase init
   firebase use --add $PROJECT
   rm -rf functions
   cp -r ../functions-samples/typescript-getting-started/functions functions
   ```
5. Install the dependencies and deploy
   ```
   cd functions
   yarn     # or npm install
   npm run deploy
   ```

Note: with TypeScript you need to build the JavaScript files before
deploying, so there's an npm script that does the steps.  You can see
that and a few other handy shortcuts in [package.json](functions/package.json)

After the deploy is complete, you will see output with the URL of your
Cloud Function endpoint. You can test the function with curl.  The following
command will work with any project, since the output of `firebase use` is
the current project ID:
```
curl https://us-central1-$(firebase use).cloudfunctions.net/helloWorld
```
