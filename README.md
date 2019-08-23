# Sapper and Tailwind Template (+ Firebase Hosting)

Boilerplate template for Sappert + Tailwind with some added Firebase hosting (serverless)!

```bash
npm install # or yarn!
npm run watch:tailwind # in a separate terminal window
npm run dev # in a separate terminal window
```

Open up [localhost:3000](http://localhost:3000) and start clicking around.

## Thanks

Inspired by:
*  The [sapper.svelte.dev](https://sapper.svelte.dev) project.
*  This [firebase and sapper](https://dev.to/eckhardtd/how-to-host-a-sapper-js-ssr-app-on-firebase-hmb) tutorial from [Eckhardt](https://github.com/Eckhardt-D)
*  This [AWS Serverless Sapper Template](https://github.com/alexdilley/sapper-serverless-template) from [Alex Dilley](https://github.com/alexdilley)

## Firebase Hosting

In your project directory:

```bash
firebase login # if you haven't already
firebase init functions hosting # then follow the prompts - say No to creation of gitigore, index etc.
firebase serve
````