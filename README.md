# 🌼 Setting up .NET Core with TailwindCSS + DaisyUI

This guide explains how to add **TailwindCSS** and **DaisyUI** to a .NET Core project (e.g., Blazor Server, Razor Pages, or MVC).  
You’ll set up TailwindCSS with the CLI, configure it for minified CSS output, and use DaisyUI components in your app.

---

## 1. Initialize an NPM package
Open a terminal in your **project folder** (⚠️ not the solution folder) and run:

```bash
npm init -y
npm i -D tailwindcss@latest @tailwindcss/cli@latest daisyui@latest

2. Add TailwindCSS + DaisyUI to your CSS

Locate your main CSS file (commonly wwwroot/css/site.css) and add:

@import "tailwindcss";
@plugin "daisyui";

3. Generate the .min.css file

We’ll generate a production-ready CSS file (site.min.css) from your development CSS (site.css).

    Input: wwwroot/css/site.css

    Output: wwwroot/css/site.min.css

Now update your layout (e.g., Pages/Shared/_Layout.cshtml) to use the minified version:

<link rel="stylesheet" href="~/css/site.min.css" asp-append-version="true" />

    ℹ️ asp-append-version automatically appends a cache-busting hash to the file name, so browsers only reload it when changes are made.

4. Add a Tailwind watch script

Edit your package.json and add a watch command:

"scripts": {
  "watch": "npx @tailwindcss/cli -i wwwroot/css/site.css -o wwwroot/css/site.min.css --watch"
}

5. Run Tailwind in watch mode

Keep Tailwind running in the background so CSS updates automatically:

npm run watch

Example output:

> projectname@1.0.0 watch
> npx @tailwindcss/cli -i wwwroot/css/site.css -o wwwroot/css/site.min.css --watch

/*! 🌼 daisyUI 5.0.9 */
≈ tailwindcss v4.0.17
Done in 225ms
