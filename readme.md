### Workspace init with pnpm

# Steps:

1. Start a pnpm project with the command: `pnpm i`
2. Initialize a git repository in the root folder with the command: `git init`
3. Create the apps/projects you want to include as subfolders from the root folder. Make sure to also use pnpm
4. Add a `scripts` property in the root package.json
5. To use every sub-project scripts follow the next steps:
- Start adding the property you will later use as an execution command. I.e: `dev:back` to run the backend project in watch mode with the command `pnpm run dev:back`
- The value of each script should follow this pattern: `pnpm --filter=folder-name run project-execution-command` 
    - `--filter=<folder name>` specifies which sub-project to target
    - `run <sub-project-script>` executes the specified script within that sub-project

6. Add additional commands if needed:
- If any additional command is needed, add them in the `scripts` property of the respective sub-project's package.json, then make the reference in the root package.json script
