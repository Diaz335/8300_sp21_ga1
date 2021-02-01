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
cp /fs/ess/PAS1855/users/diaz335/week03/pracs_sp21_ga1.md README.md
git add README.md
git status
git commit -m "Updated with markdown of assignment and comments on the previous steps"

echo "**BOLD FONT**" >> README.md
git add README.md
git status
git commit -m "added bold text, second commit as directed by assignment"
git log
```

Part3
```
mkdir data
cd data
touch sample{001..100}_R{A,B,C,D,E}_001.txt
git add *
git status
git commit -m "Added the data, 100 txt files for five samples"

```

Part4
```
#Creating and moving to new branch to rename data files
git branch data_rename
git checkout data_rename
for i in *.txt
    do
    NEWNAME="${i/%.txt/.csv}"
    mv -- "$i" "$NEWNAME"
    done
git add --all
git commit -m "changed txt file to .csv using a for loop"
#move back to master branch
git checkout master          
git merge data_rename -m "updated data file to have csv rather then txt files"

git log --oneline --all --graph 
#delete branch since already copied over
git branch -d data_rename

echo "added data .txt files and used a for loop to change to .csv files" >> README.md
git add README.md
git commit -m " describe the addition of data files"

git remote add origin git@github.com:Diaz335/8300_sp21_ga1.git
git branch -M main
git push -u origin main