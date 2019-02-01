

## This is a file relay repository  

+  After big file transmition, please do clean bellow:  

First error bellow occured  
***Cannot open existing pack file '.git/objects/pack/pack-*.idx'***  

You can repack your repository like this:  
 + git gc --auto  
 + git repack -d -l  

## find top 5 big file  
+ git verify-pack -v .git/objects/pack/pack-*.idx | sort -k 3 -g | tail -5  

+ git rev-list --objects --all | grep file id `string`  

+ git filter-branch --index-filter 'git rm --cached --ignore-unmatch <your-file-name>'  
+ rm -rf .git/refs/original/  
+ git reflog expire --expire=now --all  
+ git fsck --full --unreachable  
+ git repack -A -d  
+ git gc --aggressive --prune=now  
+ git push --force  

##### Good Luck!  

## sharkka  

