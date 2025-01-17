2: You can set your Git username and email locally on your device by using the command line:
Sol: git config user.name "FIRST_NAME LAST_NAME" 
     git config user.email "MY_NAME@example.com" 

2: You can also set your Git username and email globally on your device by using the command line:
Sol: git config --global user.name "FIRST_NAME LAST_NAME" 
     git config --global user.email "MY_NAME@example.com" 
Reference : https://stackoverflow.com/questions/6116548/how-to-tell-git-to-use-the-correct-identity-name-and-email-for-a-given-project


3: Verify your configuration by displaying your configuration file with the command:
Sol: cat .git/config

4: How to know the git username and email saved during configuration?
Sol: git config --list
Reference : https://stackoverflow.com/questions/46941346/how-to-know-the-git-username-and-email-saved-during-configuration

5: How to determine the URL that a local Git repository was originally cloned from

6: What are the Difference between these commands 
   git remote -v
   git remote show 
   git remote get-url orgin  
   git remote show origin
   git config --get remote.origin.url
Reference : https://stackoverflow.com/questions/4089430/how-to-determine-the-url-that-a-local-git-repository-was-originally-cloned-from