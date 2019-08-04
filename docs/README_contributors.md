# angular-cli-ghpages: README for contributors

## How to start <a name="start"></a>

tl;dr – execute this:

```
cd src
npm i
npm run build
npm test
```


## Local development <a name="local-dev"></a>

If you want to try the latest package locally without installing it from npm, use the following instructions.
This may be useful when you want to try the latest non published version of this library or you want to make a contribution.

Follow the instructions for [checking and updating the Angular CLI version](#angular-cli) and then link the package.


### 1. Angular CLI <a name="angular-cli"></a>

1. Install the next version of the Angular CLI.

   ```sh
   npm install -g @angular/cli@next
   ```

2. Run `ng --version`, make sure you have angular CLI v8.3.0-next.0 or greater.

3. Update your existing project using the command:

   ```sh
   ng update @angular/cli @angular/core --next=true
   ```


### 2. npm link

Use the following instructions to make `angular-cli-ghpages` available locally via `npm link`.

1. Clone the project

   ```sh
   git clone https://github.com/angular-schule/angular-cli-ghpages.git
   cd angular-cli-ghpages
   ```

2. Install the dependencies

   ```sh
   cd src
   npm install
   ```

3. Build the project:

   ```sh
   npm run build
   ```

4. Create a local npm link:

   ```sh
   cd dist
   npm link
   ```


### 3. Adding to an Angular project - ng add <a name="local-dev-add"></a>

Once you have completed the previous steps to npm link the local copy of `angular-cli-ghpages`,
follow these steps to use it in a local angular project.

1. Enter the project's directory

   ```sh
   cd your-angular-project
   ```

2. Add the local version of `angular-cli-ghpages`.

   ```sh
   npm link angular-cli-ghpages
   ```

3. Now execute the schematic.

   ```sh
   ng add angular-cli-ghpages
   ```

4. Now you can deploy your angular app to Github pages.

   ```sh
   ng run your-angular-project:deploy
   ```

5. You can remove the link later by running `npm unlink`


### 4. Testing <a name="testing"></a>

Testing is done with [Jest](https://jestjs.io/).
To run the tests:

```sh
cd angular-cli-ghpages/src
npm test
```





## Testing the standalone CLI

To quickly test the file `engine.ts` directly, the standalone mode is the best option.
Use VSCode and debug the task `Launch Standalone Program"`.


## Publish to npm

```
cd angular-cli-ghpages/src
npm run build
npm run test
npm publish dist
```