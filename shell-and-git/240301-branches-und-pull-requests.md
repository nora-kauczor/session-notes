# branches and pull requests

## repo erstellen und mit github verknüpfen/hochladen

- `mkdir new-project`
- `cd new-project`
- code ., Datei erstellen und etwas darin schreiben
- add
- commit
- repo erstellen (remotely)
- `git remote add origin link` mit link des Remote-Repos
- `git push -u origin main`

## branches workflow

### erstellen, ..., pull request

- create branch (local) | `git switch -c branchname` | `git switch -c feature/feature-name`
- write code/make changes
- add | `git add .` | git add --all <br>Wenn nur bestimmte Datei: `git add filename`
- commit | `commit -m 'commit message'`
- push branch | `git push -u origin branchname`
- pull request stellen (remotely)
- Falls Änderungen nötig sind: Nochmals lokal ändern, adden, committen, pushen und pull request stellen

### merging

- merge branch into main (remotely) | per button dort
- delete branch (remotely) | per button dort
- zu main wechseln (locally) | `git switch main`
- neues main pullen | `git pull origin main` | `git pull` sollte auch reichen, da man sich ja in main befindet
- delete branch (locally) | `git branch -d branchname` | ggf. `git branch -D branchname`

### außerdem

- anzeigen, welche branches es (lokal) in dem repo gibnt, in dem wir uns befinden | `git branch`
- tipp: terminal in VS code öffnen um dort besser zu sehen, ob man sich auf main oder einem branch befindet (?)
- einfach so main pushen (macht man normalerweise natürlich nicht..): `git push origin main`

[Cheatsheet von Merle](https://neuefische-students.slack.com/archives/C06KW9DAUF5/p1709308803934359)<br>
[Hand-out](sessions/git-branches-and-prs/git-branches-and-prs.md)<br>
[Git_Befehle](https://git-scm.com/docs/)
