# My Git Mastery Challenge Journey

## Student Information
- Name: Puram Naga Kanthi Alekhya
- Student ID: 23A91A61B7
- Repository: https://github.com/alekhya178/git-solved-23A91A61B7
- Date Started: 28-10-2025
- Date Completed: 28-10-2025

## Task Summary
Cloned instructor's repository with pre-built conflicts and resolved all 
merge conflicts across multiple branches using proper Git workflows.

## Commands Used

| Command | Times Used | Purpose |
|---------|------------|----------|
| git clone | 1 | Clone instructor's repository |
| git checkout | 20+ | Switch between branches |
| git branch | 10+ | View and manage branches |
| git merge | 2 | Merge dev and conflict-simulator into main |
| git add | 30+ | Stage resolved conflicts |
| git commit | 15+ | Commit resolved changes |
| git push | 10+ | Push to my repository |
| git fetch | 2 | Fetch updates from instructor |
| git pull | 1 | Pull updates |
| git stash | 2 | Save temporary work |
| git cherry-pick | 1 | Copy specific commit |
| git rebase | 1 | Rebase feature branch |
| git reset | 3 | Undo commits (soft/mixed/hard) |
| git revert | 1 | Safe undo |
| git tag | 2 | Create release tags |
| git status | 50+ | Check repository state |
| git log | 30+ | View history |
| git diff | 20+ | Compare changes |

## Conflicts Resolved

### Merge 1: main + dev (6 files)

#### Conflict 1: config/app-config.yaml
- **Issue**: Production used port 8080, development used 3000
- **Resolution**: Created unified config with environment-based settings
- **Strategy**: Keep production as default, add dev as optional
- **Difficulty**: Medium
- **Time**: 15 minutes

#### Conflict 2: config/database-config.json
- **Issue**: Different database hosts and SSL modes
- **Resolution**: Created separate profiles for production and development
- **Strategy**: Restructured JSON to support both environments
- **Difficulty**: Medium
- **Time**: 10 minutes

#### Conflict 3: scripts/deploy.sh
- **Issue**: Different deployment strategies (production vs docker-compose)
- **Resolution**: Added conditional logic based on DEPLOY_ENV variable
- **Strategy**: Made script handle both environments dynamically
- **Difficulty**: Hard
- **Time**: 20 minutes

#### Conflict 4: scripts/monitor.js
- **Issue**: Different monitoring intervals and log formats
- **Resolution**: Environment-based configuration object
- **Strategy**: Used process.env.NODE_ENV to determine behavior
- **Difficulty**: Medium
- **Time**: 15 minutes

#### Conflict 5: docs/architecture.md
- **Issue**: Different architectural descriptions
- **Resolution**: Merged both descriptions into comprehensive document
- **Strategy**: Created sections for each environment
- **Difficulty**: Easy
- **Time**: 10 minutes

#### Conflict 6: README.md
- **Issue**: Different feature lists and version numbers
- **Resolution**: Combined all features with clear environment labels
- **Strategy**: Organized features by category
- **Difficulty**: Easy
- **Time**: 10 minutes

---

### Merge 2: main + conflict-simulator (6 files)

#### Conflict 1: config/app-config.yaml  
- **Issue**: Main branch contained production parameters, while conflict-simulator introduced testing configurations for simulated runs.  
- **Resolution**: Integrated both by allowing configuration toggling between production and simulator modes.  
- **Strategy**: Added an `environmentMode` variable to manage settings dynamically.  
- **Difficulty**: Medium  
- **Time**: 15 minutes  

#### Conflict 2: config/database-config.json  
- **Issue**: Database hosts and credentials differed for simulator and production setups.  
- **Resolution**: Combined both configurations using environment-based profile separation.  
- **Strategy**: Introduced `SIMULATION_DB` and `PRODUCTION_DB` keys for clear context switching.  
- **Difficulty**: Medium  
- **Time**: 10 minutes  

#### Conflict 3: docs/architecture.md  
- **Issue**: The main branch contained finalized architectural flow, while conflict-simulator added experimental testing components.  
- **Resolution**: Merged both by adding a subsection highlighting simulated workflow integration.  
- **Strategy**: Retained existing structure but appended simulator architecture as an optional section.  
- **Difficulty**: Easy  
- **Time**: 8 minutes  

#### Conflict 4: scripts/deploy.sh  
- **Issue**: Deployment logic conflicted — main handled live deployment, simulator branch had test-run automation.  
- **Resolution**: Unified both using conditional logic to detect runtime mode and deploy accordingly.  
- **Strategy**: Added a shell condition checking `$MODE` (production/simulator).  
- **Difficulty**: Hard  
- **Time**: 20 minutes  

#### Conflict 5: scripts/monitor.js  
- **Issue**: Simulator branch logged mock metrics, while main monitored real-time data.  
- **Resolution**: Integrated both logging systems using an environment-based flag.  
- **Strategy**: Added an if-statement checking `process.env.MODE` to switch log sources dynamically.  
- **Difficulty**: Medium  
- **Time**: 12 minutes  

#### Conflict 6: README.md  
- **Issue**: Both branches had overlapping setup and feature descriptions.  
- **Resolution**: Merged all sections, preserving stable documentation while including a new “Simulation Mode” section.  
- **Strategy**: Retained production instructions at the top and appended simulation usage details separately.  
- **Difficulty**: Easy  
- **Time**: 10 minutes  

#### Summary:
This merge primarily focused on integrating **simulation-based testing features** with the existing **production-ready codebase**. Compared to the first merge, it required deeper attention to configuration and conditional logic. This phase enhanced my understanding of maintaining environment consistency and writing merge commits that preserve both stability and flexibility.

---

## Most Challenging Parts

1. **Understanding Conflict Markers**: Initially confused by `<<<<<<<`, `=======`, `>>>>>>>` symbols. Learned that HEAD is current branch and the other side is incoming changes.
2. **Deciding What to Keep**: Hardest part was choosing between conflicting code. Learned to read both versions completely before deciding.
3. **Complex Logic Conflicts**: deploy.sh had completely different logic. Had to understand both approaches before combining.
4. **Testing After Resolution**: Making sure resolved code actually worked was crucial.

## Key Learnings

### Technical Skills
- Mastered conflict resolution process
- Understood merge conflict markers
- Learned to use git diff effectively
- Practiced all major Git commands

### Best Practices
- Always read both sides of conflict before resolving
- Test resolved code before committing
- Write detailed merge commit messages
- Use git status frequently
- Commit atomically

### Git Workflow Insights
- Conflicts are normal, not errors
- Take time to understand both changes
- When in doubt, ask for clarification
- Document your resolution strategy 
- Keep calm and read carefully

## Reflection
This challenge taught me that merge conflicts aren't scary - they're 
just Git asking "which version do you want?". The key is understanding 
what each side is trying to do before combining them. I now feel 
confident handling conflicts in real projects.

The hands-on practice with all Git commands (especially rebase and 
cherry-pick) was invaluable. I understand the difference between merge 
and rebase, and when to use each. Most importantly, I learned that 
git reflog is a lifesaver!
