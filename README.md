# forge-setup

Steps
1. setup repository in GitHub with .gitignore, readme, and license
2. clone repository via https to some directory on local machine
3. set url of remote origin in git bash with `git remote set-url origin git@github.com:username/your-repository.git`
4. download most recent forge mdk and extract its contents
5. copy contents to local repository, commit and push to remote
6. in Eclipse choose File -- Import -- Gradle project and choose the local repository directory
7. wait for Eclipse to finish importing the project
8. commit newly generated files to repository
9. at the bottom in Grade tasks choose runClient to launch Minecraft and see if the mod works

If the above steps worked you can proceed as follows:
1. change mod information in build.gradle file (version, group, archivesBaseName)
2. change modid in (approx.) line 103 under data -- workingDirectory -- args
3. change information for jar manifest (approx. after line 147)
4. runClient and see if everything still works
5. run Gradle task `build` and check that jar is generated in build -- libs directory of repository
6. add `/run/` to .gitignore
