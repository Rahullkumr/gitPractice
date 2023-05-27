# Introduction to Git (Google)

## Module 1
1. Your colleague sent you a patch called fix_names.patch, which fixes a config file called fix_names.conf. What command do you need to run to apply the patch to the config file?
  ```diff
 'diff names.conf fix_names.conf
 
 'patch fix_names.conf names.conf
 
+ patch fix_names.conf < fix_names.patch

 'diff names.conf_orig names.conf_fixed > fix_names.conf
```

2. You're helping a friend with a bug in a script called fix_permissions.py, which fixes the permissions of a bunch of files. To work on the file, you make a copy and call it fix_permissions_modified.py. What command do you need to run after solving the bug to send the patch to your friend?

## Module 2

## Module 3

## Module 4
