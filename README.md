# reminder-template for Purescript projects

This is my new-to-purescript take on a robust method of creating new projects, based on articles by 
the following authors
- Charles Scalfani, Functional Programming Made Easier
- https://github.com/JordanMartinez/purescript-jordans-reference/blob/latestRelease/31-Design-Patterns/09-Project-Prelude.md
- https://github.com/megamaddu/purescript-react-basic-hooks/blob/main/docs/getting-started.md

## Command line apps

1. Create new project on github: Set Public, Add README, skip .gitignore for now, set MIT License
2. On local machine: git clone <github URL/project-name.git>, this creates
- project-name folder containing
- LICENSE file
- README.md file
- .git hidden infrastructure folder and contents
3. npm init -y (recommend using nvm or n for node & hence npm version control), creates
- package.json which includes repository remote URL
4. Local, NOT global, npm i -D purescript spago, creates
- package-lock.json
- node_modules folder with 100s of files
- new entry in package.json "devDependencies": { "purescript": "^0.x.y", "spago": "^0.a.b" }
5. npx spago init, creates
- src/Main.purs
- test/Main.purs
- .gitignore which reduces files tracked by git from 100s to <10
- .purs-repl with content import Prelude
- packages.dhall points to recent package psc-0.x.y-YYYYMMDD semver compat with purescript version
- spago.dhall points to above, src/, test/ and a few purescript dependencies
6. npx spago build, creates
- .spago folder containing the few purescript dependencies
- output folder containing about 60 js modules including Prelude which exports about 55 values
- .psc-ide-port content nnnnn which indicates VS code language server is running
7. npx spago run, check for output at terminal
8. add an AppPrelude.purs file to stand in for the both the Prelude and project specific imports

It is easy to forget the npx prefixes required with local installs of compiler. If global installs are present at same time, this will lead to non-intuitive error messages relating to incompatible purescript and package-set versions. Much safer to delete any global installs if not needed for other projects.

## Web apps

to follow


