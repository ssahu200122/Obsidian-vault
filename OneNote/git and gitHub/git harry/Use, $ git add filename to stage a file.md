> [!caution] This page contained a drawing which was not converted.

# Use, ==$ git add <filename>== to stage a file
 
# Use, ==$ touch <filename>== to create file in the directory using git
 
# Use, ==$ git add -A== to add multiple files to staging area
 
# Use, ==$ git commit -m "<comment>"== to commit
 
# Use, ==$ git checkout <filename>== to match to the previously modified version
 
# Use, ==$ git checkout -f== to match to all the file to previously modified versions
 
# To view the commit history use,  
==$ git log==
 
# To view last n commit history use,  
==$ git log -p -n==
 
# Use, ==$ git diff== to compare file from working area to staging area
 
# To compare staging area to last commit use,  
==$ git diff --staged==
 
# To directly commit files (skipping staging) use,  
==$ git commit -a -m "<comment>"==
 
# To remove file from commit to modified use,  
==$ git rm --cached <filename>==
 
# To remove file completely use,  
==$ git rm==