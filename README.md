# react-svelte-compare

### A point-by-point comparison of "how to's" in React vs. Svelte.

I'm not going to get into the internals (much), so, not much about the compiler in Svelte vs. the virtual DOM in React.
Nor am I going to get bogged down in editorializing. Just, "how do you do this?", so you can quickly switch between one and
the other _and get stuff done_.

## Starting a project, both React and Svelte

For either library:
* First, you must be well-grounded in HTML, CSS, and modern JavaScript.
* Install Node.js.
* Find your command line (for example, Terminal on MacOS).

Now you can run:
`npm create vite@latest`

This will ask you for a project name, then for a framework (options include both React and Svelte, amongst others), then it will ask whether you want to use TypeScript or JavaScript. I will be using JavaScript for these examples, just to have
shorter code, but you can easily translate.

After scaffolding the project (i.e., creating a starting point set of folders and files, including a bunch of 
boilerplate-y stuff), it will give you further instructions. Assuming you named your project "myproject", there will be
a project folder named "myproject", and the instructions will be:

```
cd myproject
npm install
npm run dev
```
When you run `npm run dev` a running version of your project can be viewed at the URL it will show on-screen, such as
`http://localhost:5173/`. The starting point of your project will be a page that says "Vite + React" or "Vite + Svelte"
(depending on which type of project you chose).

It behooves you to put your project directory into some kind of source code control system _now_.

You'll be editing the source code files in your project directory to add functionality.

_Notes:_ 

* Older documentation will say that the command to create a React app is `npx create-react-app my-app`. That is out
of date. Now that Vite exists, `create-react-app` is deprecated.

* [The Svelte documentation](https://kit.svelte.dev/docs/creating-a-project) will suggest the command `npm create svelte@latest my-app`. This would create a SvelteKit project, rather than just a Svelte project. SvelteKit is to Svelte as Next.js is to React (approximately). The scope of frameworks such as SvelteKit and Next.js is greater than just UI DOM rendering, which is what I'm focusing on here. You can create a framework project (such as SvelteKit or Next.js) to play with these things, but it will contain distracting other stuff that I'm ignoring for now.

