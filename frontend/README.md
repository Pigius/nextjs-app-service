

# NextJS app as a static HTML

This repository comes from the official NextJS [repository](https://github.com/vercel/next.js/tree/canary/examples/with-styled-components), and is used for the purpose of showing how you can do NextJS application deployment using the Serverless [Lift](https://github.com/getlift/lift) plugin, along with construct [static-webiste](https://github.com/getlift/lift/blob/master/docs/static-website.md)).

Before the deployment, the application we need to export the NextJS app to static HTML.

Fortunately, NextJS allows export to [static html](https://nextjs.org/docs/advanced-features/static-html-export). All we had to do was change the configuration slightly in `package.json`


```json
...
"build": "next build && next export",
...
```


## Setup

```bash
npm install
npm run build
```

Above commands will install all packages, build the project, and export it into the statics html within the `out` folder.

## Important

Please consider that not every NextJS project can be exported to static HTML. Not all functionalities are compatible with `next export`.

So you could see errors like:

```bash
Error: Image Optimization using Next.js' default loader is not compatible with `next export`.
```

# Deployment

The process involved in deployment will be done through `Serverless Framework` from the root of this project.
