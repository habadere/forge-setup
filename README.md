# forge-setup

Steps
1. setup repository in GitHub with `.gitignore, readme, license` files
2. in some local directory open Git Bash:
  - clone repository to new folder: `git clone https://www.github.com/username/yourrepository.git`
  - set url of remote origin: `git remote set-url origin git@github.com:username/yourrepository.git`
3. download most recent forge mdk and extract its contents
4. copy contents to local repository, commit and push to remote
  - stage all: `git add --all`
  - commit: `git commit -m "Commit message"`
  - push: `git push`
5. in Eclipse choose File -- Import -- Gradle project and choose the local repository directory
6. wait for Eclipse to finish importing the project
7. commit newly generated files to repository
8. at the bottom in Gradle tasks choose `runClient` to launch Minecraft and see if the mod works

If the above steps worked you can proceed as follows:
1. add `/run/` to the `.gitignore` file
2. change mod information in `build.gradle` file
  - `version`
  - `group`
  - `archivesBaseName`
  - change modid in (approx.) line 103 under `data -- workingDirectory -- args`
  - change information for jar manifest (approx. after line 147)
3. `runClient` and see if everything still works
4. run Gradle task `build` and check that jar is generated in build -- libs directory of repository

Keep adjusting the mod information:
1. in the local repository under `src\main\java\com\yourname\modname`
  - change name of directory of package `yourname`
  - change name of directory of `modname`
  - change filename `modname.java` in directory `modname`
  - change class name and constructor in `modname.java` to match `modname`
  - in (approx.) line 21 of `modname.java` adjust `@Mod(modid)` (must not include `-`)
2. in the local repository under `src\main\resources\META-INF` edit the `mods.toml` file
  - in (approx.) line 18 change `modid`
  - in (approx.) line 44 and 56 change `modid`
