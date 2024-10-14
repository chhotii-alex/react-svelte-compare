# react-svelte-compare

### A point-by-point comparison of "how to's" in React vs. Svelte.

I'm not going to get into the internals (much), so, not much about the compiler in Svelte vs. the virtual DOM in React.
Nor am I going to get bogged down in editorializing. Just, "how do you do this?", so you can quickly switch between one and
the other _and get stuff done_.

## Starting a project

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

## What are Components, and Creating the Most Minimal Component

Both a Svelte UI and a React UI are composed of components. Much of your time coding may be spent defining components. 
Think of components as classes (in the OOP sense) that are specialized for creating specific subtrees in the DOM. (Are they
actually classes? Is JavaScript actually an object-oriented programming language? Let's talk about that... at the pub...
with beer in hand... later.) Just like with a class, you may have multiple instances of a component in play at once, and 
each instance may have its own data (whether we call that attributes, properties, state, member variables... it's all data).

Both Svelte and React assume that you know and love HTML and thus the most natural way to specify some piece of the DOM
is to use HTML... or rather, something that looks a whole lot like HTML. Both use HTML-like syntax with some enhancements
and minor modifications. 

Whether you've created a React project or a Svelte project, the base project includes one starter component, named App.
In either case, the code for App is in your `src/` folder. Let's strip out all but the most minimal content from App, and
build up from there.

In React, your App will be defined in `App.jsx`, whereas in Svelte, it will be `App.svelte`. Delete everything in this file and replace in entirety with the code below.

In React, the new code is:
```
export default function App() {
    return <h1>Hello, Web Programming!</h1>
}
```
What, is that chocolate, I mean HTML in my JavaScript? JSX is an extension of JavaScript that lets you just burst into song,
I mean, HTML (with some interesting additions and some slight restrictions).
In Svelte, the new code is just:
```
<h1>Hello, Web Programming!</h1>
```
In a `.svelte` file, anything that is not inside a `<script></script>` or a <style></style> is treated as HTML (again,
with some additions and little differences).

Save the updated App file and the UI in your browser should instantly update to just the new content.

## Variable Interpolation

You're not here to just create static HTML content, so, let's have a variable. Edit your App component source code.

In React, add
```
let name = 'Fred';
```
as the first line of your .jsx file. (Later on, we'll get into _state_ and _stores_ and such, and rethink where your data
is set, but for now, let's just make there be a variable.)

On the other hand, in Svelte, this needs to be inside a script tag. Recall that if it's not in a script tag, it's not 
treated as JavaScript&mdash;you don't want this considered HTML. Thus, add this somewhere in your .svelte file:
```
<script>
    let name = 'Fred';
</script>
```

In either case, you can now _interpolate_ your variable into your HTML. Change `<h1>Hello, Web Programming!</h1>` to `<h1>Hello, {name}!</h1>` and as soon as you save the source file, you should see the greeting change to __Hello, Fred!__

## next

## dynamic attributes

Restrictions on HTML in JSX
, such as:
* You cannot use `class` as an attribute name: use `className` instead
* You cannot use `for` as an attribute name: use `htmlFor` instead
* If an HTML expression spans more than one line, it must be surrounded by parentheses
* An HTML expression must consist of only one top-level node and its children
