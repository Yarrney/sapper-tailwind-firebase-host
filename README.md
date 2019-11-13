# Sapper and Tailwind Template (+ Firebase Hosting)

Boilerplate template for Sappert + Tailwind with some added Firebase hosting (serverless)!

```bash
npm install # or yarn!
npm run watch:tailwind # in a separate terminal window
npm run dev # in a separate terminal window
```

Open up [localhost:3000](http://localhost:3000) and start clicking around.

[Sample Website](https://sapper-tailwind-firebase.firebaseapp.com)

## Thanks

Inspired by:
*  The [sapper.svelte.dev](https://sapper.svelte.dev) project.
*  This [firebase and sapper](https://dev.to/eckhardtd/how-to-host-a-sapper-js-ssr-app-on-firebase-hmb) tutorial from [Eckhardt](https://github.com/Eckhardt-D)
*  This [AWS Serverless Sapper Template](https://github.com/alexdilley/sapper-serverless-template) from [Alex Dilley](https://github.com/alexdilley)
*  This [Sapper Firestore Setup Example](https://github.com/sveltecasts/009-sapper-firestore) from [Sveltecasts](https://github.com/sveltecasts) - also, his [YouTube Video](https://www.youtube.com/watch?v=8Wpab4VjgQQ) gave me a chuckle! 

## Firebase Hosting

In your project directory:

In your terminal window, type the two following commands.  You'll be prompted on the `init` command to enter some additional details (same with `login`), but you want to make sure you don't overwrite the index.js file (it already exists).
```bash
firebase login # if you haven't already
firebase init functions hosting

? What language would you like to use to write Cloud Functions? JavaScript
? Do you want to use ESLint to catch probable bugs and enforce style? No
? File functions/package.json already exists. Overwrite? No
i  Skipping write of functions/package.json
? File functions/index.js already exists. Overwrite? No
i  Skipping write of functions/index.js
? File functions/.gitignore already exists. Overwrite? Yes
✔  Wrote functions/.gitignore
? Do you want to install dependencies with npm now? Yes
```

Then go into your `package.json` and update the node to v10.
```json
"engines": {
  "node": "10"
},
```

Finally, you want to 
```bash
cd functions
npm install # express sirv compression polka
npm run deploy
````

Note using `firebase serve` doesn't play well with Tailwind in this config (it's a known issue), however I've chosen to go down the dev + build and not concern myself with the serve function in firebase. 