`open .` ordner in finder öffnen

| command                           | functionality                                     |
| --------------------------------- | ------------------------------------------------- |
| **...**                           |                                                   |
| `git switch -c <branchname>`      | create a new branch and switch to it              |
| `git switch <branchname>`         | switch branches                                   |
| `git switch main`                 | switch to main                                    |
| `git branch`                      | list your branches                                |
| `git branch -a`                   | list all branches (local and remote)              |
| `git branch -d <branchname>`      | delete a branch                                   |
| **...**                           |                                                   |
| `rm -rf <folder_name>`            | folder (auch repo) löschen obwohl sie inhalte hat |
|                                   |                                                   |
| `git pull origin main`            |                                                   |
| `git pull`                        |                                                   |
| `git push origin main`            |                                                   |
| `git push -u origin <branchname>` |                                                   |
| `git push`                        |                                                   |
|                                   |                                                   |
| `git init`                        | turn folder into git repo (locally)               |
|                                   |                                                   |
|                                   |                                                   |
|                                   |                                                   |
|                                   |                                                   |
|                                   |                                                   |
|                                   |                                                   |
|                                   |                                                   |

22.03.24 problem

- mit code . öffnet sich zwei mal vs code, zwei mal wird das gleiche project geöffnet, einmal unter richtigem namen, einmal als "untitled workspace"
- wenn man im terminal oder finder sich das anschaut sieht man nur einen ordner mit dem richtigen namen
- `ls -a` um verstecktes zu sehen
- tatsächlich lag die kopie des richtigen projects im components-ordner (also darin verschachtelt), war aber kein eigenes repo
- unklar, warum vs code zwei fenster geöffnet hat, lag nicht an der frage ob repo oder kein repo, vllt sowas wie das pro index.js ein fenster öffnet oder so
