# cc_recipes
My personal Clear Case cheatsheet

## Views
Setting the working view:

    ct setview <view_name>

Removing a view (don't forget to save the cs!):

    ct rmview -tag <view_name>
    
List name of actual view:

    ct pwv
    
List available views (depending on environment can be load-intense):

    ct lsview
    
Get properties for a view:

    ct lsview -pro -ful <view_name>

## Configspec
Dump actual view's configspec:

    ct catcs
    
Edit actual view's configspec with default editor:

    ct edcs
    
Set the configspec to a certain file:

    ct setcs <file_name>

## Elements manipulation
Add a directory to a cc project:

    ct mkelem -mkpath <dir_name>
    
Add a file to a cc project:

    ct mkelem -nc <file_name>
    
Search for elements created in a time window:

    ct find . -version "{created_since(dd1-mm1-yyyy1) && \!created_since(dd2_mm2_yyyy2)}" -print
    
Clean a view of all untracked files (use with due care):

    ct lsprivate | grep -v checkedout | xargs /bin/rm -rf
    
Find /0 elements that are LATEST in <branch_name>:

    ct find . -type f -version "version(.../<branch_name>/LATEST)&&version(.../<branch_name>/0)" -print


    
