# Template Zine
A barebones [Zine](https://github.com/kristoff-it/zine) template, for Zig/Zine stable releases.

# Usage
- Click `Use this template` -> `Create new repository`
- Name and create your repository
- Clone it with git
- Change the `.name` and `version` inside `build.zig.zon` to whatever you want. (Changing the .name field also invalidates the .fingerprint value)
- Run `zig build` it will generate a new `.fingerprint` value, replace the old value with the new one.
- Run `zig build serve` to startup a server
- Make your static site!

# Older templates
Because GitHub templates don't have any versioning scheme, older templates are available as branches  
- Tick `Include all branches` box when creating your repository
- Switch the default branch to the version you want to use
- Remove all other branches
- Rename the branch to main/master
- Follow regular usage instructions

# Manually updating Zine version
Sometimes new Zig updates break Zine and a tagged release can take some time. You can change the package url to use main instead.
- Change `.url` field in `build.zig.zon` to `git+https://github.com/kristoff-it/zine?ref=main`
- Go to the [Zine main branch](https://github.com/kristoff-it/zine/commits/main/)
- Click the commit you want (or latest) and copy the full hash at the end of url
- Append `#` and the full hash from the URL.
    - Example `git+https://github.com/kristoff-it/zine?ref=main#717b3afec72438ffed364e04c7ca33aa5d4fa5cb`
- Run `zig build`, the `.hash` field will be invalid, copy/paste the new hash the compiler gives you.
- Run `zig build serve`, the new version will be fetched and if nothing is wrong, the server will spin-up.
