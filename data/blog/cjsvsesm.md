---
title: CommonJS vs ES Modules
date: '2022-07-04'
tags: ['MODULES', 'CJS', 'ESM']
draft: false
summary: CommonJS vs ECMAScript Modules
authors: ['ben']
---

CommonJS vs ECMAScript Modules

If you're already familiar with the JavaScript universe, you unquestionably come to believe that ecosystem of JS is more massive than any other language ever had. When it comes to Modular Programming, **CJS**, **AMD**, **UMD**, and **ESM** will be the commonly used approaches, and the list goes on. In this article, we will look deeper into CJS and ESM only as it's widely used.
Modular Programming is nothing but a mechanism that allows you to break up your code into separate files; this makes it easier not only to maintain the code-base, but there are some other valuable benefits behind this approach. Let's see what those are. 

Before the concept of modular programming appeared in JavaScript, Developers would create multiple files and link to them as separate scripts if they wanted to segregate their code. Here is what it looks like: 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/izj3on455hv2yy9koiyy.png)

the above approach will make two major issues:

- **Polluting the global namespace**
- **Dependency management**

**Polluting the global namespace**: All the variables you created in your scripts, exist on the window object. If you attempted to use another variable with same name in another file, it would become difficult to know which value would be used at any point in the scripts, since they would all be using the same window. The only way a variable could be private was by putting it within a function scope. 

**Dependency management**: Scripts would have to be loaded in order from top to bottom to ensure the correct variables were available.

IIFE(Immediately Invoked Function Expression); a JavaScript function that runs as soon as it is defined. Writing all code in IFFE and placed them on a single object was the immediate solution provided by the community earlier. Here is what it looks like:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3xfr9jf37fsd7x7e1wgc.png)

After that, a few module solutions emerged:

- CJS (CommonJS) is a synchronous approach implemented in Node.js as default.
- Asynchronous Module Definition (AMD), which was an asynchronous approach.
- Universal Module Definition (UMD) was intended to be a universal approach supporting both previous styles.

However, these approaches didn't seem completely useful for the client-side(JavaScript). ECMAScript finally came up with the solution ES Modules which are now available natively in JavaScript.

## ES Modules

ES Modules in JavaScript use the import and export keywords:

- **import**: Used to read code exported from another module
- **export**: Used to provide code to other modules.

ES Modules are what you see in React, Angular, or any other Front-End JavaScript Libraries/Frameworks. It will work asynchronously. It is compatible with browsers and has HTML support. It can be accessible via CDN/URL. 

When it comes to Back-End, NodeJS uses CJS as its default way to import/export packages between files; meanwhile, Deno, the hot new alternative to Node, makes ESM the default. 

To achieve the same functionality in vanilla JavaScript, you have to set the type value to the module like this: 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/67jenl78hbix53j0m89n.png)

If you want to enable ES Modules on NodeJS, you have to do something like this:

By adding `"type": "module"` to package.json, now every files will be treated as mjs(EcmaScript modules) file. Otherwise, you must create files in mjs extension to achieve the same goal.

> package.json

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/p53ij9j3pjidel4v8imn.png)

### Named Exports

> index.js

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/04npc5dzkfhqd0n9t7e3.png)

Then you can import all the exported modules from index.js to your respective file like this:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/zf90mir1xjqc95lpt9ya.png)

It is also possible to use an **as**(alias) to rename the function like this:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8z188jaysp5rkaywyhwt.png)

#### Import all modules from particular script

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bb3yfjqc2tvdtu4urr7x.png)

### Default Imports 

A file can have only one default export, but it can have multiple named exports.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xof7tsf3s9323dzuf43z.png)

A default export will not be imported with curly brackets, but will be directly imported into a named identifier.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uektgfdrl71y7pf0h66g.png)

## CommonJS 

CJS imports modules synchronously. It doesn't support either HTML or CDN/URL imports. It's not browser compatible. It will have to be transpiled and bundled. But it's suitable for the Back-End because NodeJS has CJS as its default modular. 

### Default Exports

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jclu8fbt54462lm3qwc1.png)

when you import modules via CJS; you can specify either its Module ID or path of the module inside the require method like this:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/zno2yw3bhezvroqjfw83.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pu7dh6wdrgkssqf35psq.png)

### Named Exports

> index.cjs

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/k9g96zza2dsh1euie7dt.png)

> Note here file extension is cjs but now js also can be supported.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b3w09wwaizc7c3ztfiuy.png)

Resources:

https://www.digitalocean.com/community/tutorials/understanding-modules-and-import-and-export-statements-in-javascript
https://developer.mozilla.org/en-US/docs/Glossary/IIFE
https://redfin.engineering/node-modules-at-war-why-commonjs-and-es-modules-cant-get-along-9617135eeca1
https://nodejs.org/api/modules.html


