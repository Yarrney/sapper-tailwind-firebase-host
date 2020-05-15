# Sapper and Tailwind Template (+ Firebase Hosting)

Boilerplate template for Sappert + Tailwind with some added Firebase hosting (serverless)!

```bash
# Installation
npx degit yarrney/sapper-tailwind-firebase-host 
npm install

# Development
npm run watch:tailwind
npm run dev
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

Set up a new [firebase project](https://firebase.google.com/) - we'll wait. We want to install firebase **functions** and **hosting**. Follow these instructions in your project directory:
```bash
firebase login # if you haven't already
firebase use --add #your-firebase-project-id
firebase init

# Step 1 - you want Functions and Hosting
? Which Firebase CLI features do you want to set up for this folder? Press Space to select features, then En
ter to confirm your choices. 
 ◯ Database: Deploy Firebase Realtime Database Rules
 ◯ Firestore: Deploy rules and create indexes for Firestore
❯◉ Functions: Configure and deploy Cloud Functions
 ◉ Hosting: Configure and deploy Firebase Hosting sites
 ◯ Storage: Deploy Cloud Storage security rules
 ◯ Emulators: Set up local emulators for Firebase features

# Step 2 - don't overwrite anything really... 
? What language would you like to use to write Cloud Functions? JavaScript
? Do you want to use ESLint to catch probable bugs and enforce style? No
? File functions/package.json already exists. Overwrite? No
i  Skipping write of functions/package.json
? File functions/index.js already exists. Overwrite? No
i  Skipping write of functions/index.js
? File functions/.gitignore already exists. Overwrite? Yes
✔  Wrote functions/.gitignore
? Do you want to install dependencies with npm now? Yes

# Step 3 - I know, exhausing isn't it
? What do you want to use as your public directory? static
? Configure as a single-page app (rewrite all urls to /index.html)? No

```

Note you might have to play around with this a bit to get firebase to work as you need, but I believe in you. While you're at it, let's do some tidy up:
````bash
# these files, we don't need them
rm static/index.html static/404.html
````

Then go into your `firebase.json` and update it to this. You'll need it to ensure functions can use the SSR function created. 
```json
{
  "hosting": {
    "public": "static",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [{
      "source": "**",
      "function": "ssr"
    }]
  }
}
```

Finally, you want to 
```bash
cd functions
npm install # express sirv compression polka
cd ..
npm run deploy
````

Note using `firebase serve` doesn't play well with Tailwind in this config (it's a known issue), however I've chosen to go down the dev + build and not concern myself with the serve function in firebase. 