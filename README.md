1. npm create svelte@latest
   explain routing, works directory based just like next

2. Create todo directory, make +page.svelte

3. Create simple todo - app:
   do a foreach block to show all example items
   make an input field, bind it to an input value;
   try logging this, doesnt work, make it reactive with $: in front of it.
   make the addToList function, use spread operator, not push, push will not trigger rerender.
   If you want to use push, be sure to add todos = todos

Svelte is a modern framework for building web applications. Unlike other JavaScript frameworks such as React or Vue, which do a lot of work in the browser (like creating virtual DOMs and comparing them to the actual DOM to figure out the most efficient way to make updates), Svelte shifts that work into a compile step that happens when you build your app.

That means that instead of sending a lot of JavaScript code to the client (the user's browser) and asking it to figure out how to make the page, Svelte does that work ahead of time on your own machine. As a result, the client gets less code to run and the user gets a faster, more efficient application. This approach also eliminates the need for a virtual DOM, which reduces memory usage and improves performance.

In terms of syntax, Svelte is component-based (like React and Vue), so you build your application out of self-contained, reusable pieces. It uses a superset of HTML, meaning that if you know HTML, CSS, and JavaScript, you can start writing Svelte code pretty easily.

Now, SvelteKit is a framework built on top of Svelte. It's designed to help you build full-stack applications, meaning applications that have both a frontend (the part the user interacts with) and a backend (the part that handles data, makes computations, etc.).

SvelteKit provides a lot of helpful tools and capabilities out of the box, including:

Server-side rendering (SSR): This means that your pages are generated on the server before they're sent to the user's browser, which can make your app faster and improve its SEO (search engine optimization).
Routing: SvelteKit uses a file-based routing system, similar to Next.js. This means that you can define your app's pages and their URLs simply by creating files in a certain directory structure.
API routes: Like Next.js, SvelteKit allows you to define serverless functions (pieces of backend code that run in response to HTTP requests) as part of your application.
Pre-rendering: SvelteKit can generate static HTML pages at build time, which can be served very quickly and cheaply, improving performance for users and reducing server costs.

Pros of SvelteKit:

- It offers a simpler and more intuitive API, making it easier for developers to understand and use.
- Because Svelte is a compiler, SvelteKit applications often have a smaller bundle size which leads to faster load times.
- The Svelte syntax is more straightforward, making it easier to read and write.
- SvelteKit supports both server-side rendering (SSR) and static site generation (SSG).

Cons of SvelteKit:

- It's newer and less mature than Next.js, so there may be fewer resources and less community support.
- Because it's less established, it may also have fewer plugins and integrations.
- The job market demand for Svelte and SvelteKit is currently lower than for Next.js and React.
