

# 🌼 Setup .NET Core with TailwindCSS + DaisyUI

This guide explains how to add **TailwindCSS** and **DaisyUI** to a .NET Core project (e.g., Blazor Server, Razor Pages, or MVC).  
You’ll set up TailwindCSS with the CLI, configure it for minified CSS output, and use DaisyUI components in your app.


## 1. Initialize NPM
```bash
npm init -y
npm i -D tailwindcss@latest @tailwindcss/cli@latest daisyui@latest

2. Configure CSS

In wwwroot/css/site.css add:

@import "tailwindcss";
@plugin "daisyui";

3. Generate Minified CSS

Input: wwwroot/css/site.css
Output: wwwroot/css/site.min.css

In Pages/Shared/_Layout.cshtml:

<link rel="stylesheet" href="~/css/site.min.css" asp-append-version="true" />

4. Add NPM Script

In package.json:

"scripts": {
  "watch": "npx @tailwindcss/cli -i wwwroot/css/site.css -o wwwroot/css/site.min.css --watch"
}

5. Run Watch

npm run watch
