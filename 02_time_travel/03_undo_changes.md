## Undo changes 

### Rollback: Undo staged change (git reset HEAD) 

* Situatie: 
  * Je hebt een aanpassing gedaan die je niet meer wil. De aanpassing is nog niet gecommit. 
  * IntelliJ: 
    * je hebt een aanpassing gedaan in een bestaande file en nog niet gecommit (file is blauw) 
    * of: je hebt een nieuwe file aangemaakt en toegevoegd aan git (file is groen)
    * met andere woorden: de file staat onder "Changes" in het IntelliJ-commit-venster (ctrl-k)
  * git-bash: je hebt een aanpassing gedaan en deze gestaged (git add .)
* Je wil terug naar de situatie van de laatste commit.

#### In IntelliJ
* noot: Als je in IntelliJ een aanpassing in een bestaande file doet dan is deze ook onmiddellijk gestaged 
* open het commit-window (klik op Commit in de linker marge)
* rechts-klik op "Changes"
* kies "Rollback"
* als je Unversioned Files hebt moet je deze manueel deleten

#### In Git Bash
* gebruik het commando "**git reset HEAD**"
```bash
    cd gittest
    git status
    <pas de file aan>
    git add . 
    git status
    <we willen nu de aanpassingen rollbacken:> 
    git reset HEAD
    git status
```

### Undo unstaged change: git checkout 

* Situatie:
    * Je hebt een aanpassing gedaan die je niet meer wil, deze is unstaged. 
    * IntelliJ: In IntelliJ bestaat deze situatie eigenlijk niet. 
      Als je in IntelliJ een aanpassing in een bestaande file doet dan is deze ook onmiddellijk gestaged. 
      Als je een  nieuwe file aanmaakt en deze niet add dan is dit een unstaged change. 
      Je kan deze file dan gewoon manueel deleten. 
    * git-bash: je hebt een aanpassing gedaan en deze is nog **niet** gestaged (nog geen `git add .` gedaan)
* Je wil terug naar de situatie van de laatste commit.

#### In Git Bash
* doe een checkout van de laatste commit:
```bash
    cd gittest
    git status
    <pas de file aan>
    git status
    <we willen nu de aanpassingen rollbacken:> 
    git checkout <aangepaste file>
    git status
```

### Undo last commit

* Situatie: je hebt een aanpassing gedaan en deze gecommit
* Je wil terug naar de situatie van de **vorige commit**.

#### In IntelliJ
* Ga naar de history (de "Log" tab in het Git Tool window onderaan)
* selecteer de vorige commit
* rechts-klik en kies "Reset Current Branch to here..."
* Kies in de dialog de eerste optie "Soft". 
  Je behoudt dan wel de aangepaste files, maar je kan nu kiezen of je deze files wil Rollbacken of gewoon verder wil aanpassen. 

#### In Git Bash
* gebruik het commando "**git reset HEAD~**"
```bash
    cd gittest
    git status
    <pas file aan>
    git status
    git add <file>
    git commit -m "<zet hier de commit message>"
    git status
    git log
    <we willen nu de gecommitte aanpassingen rollbacken:> 
    git reset HEAD~
    git log
    git status
```

### Oefening
* doe een aanpassing en rollback 
* doe een aanpassing, commit en undo  

---
[prev](02_go_back_in_time.md)
[next](../03_github/01_wat_is_github.md)
