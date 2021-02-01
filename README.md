#Part 1

```
#change to correct directory
cd /fs/ess/PAS1855/users/diaz335/week03/
#make new directory and move there
mkdir prac_sp21_ga1
cd prac_sp21_ga1
#load git(ensures most recent), initiate git, check status
module load git
git init
git status

#README file in Markdown, write first lines, stage and commit
touch README.md
echo "Repository for assignment 1" > README.md
git add README.md
git status
git commit -m "Started the assignment"
```

#Part2
```
#2nd .md with more content
cp /fs/ess/PAS1855/users/diaz335/week03/pracs_sp21_ga1.md READ**BOLD FONT**
**BOLD FONT**
