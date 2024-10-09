# Mitwoch

1. Github 
2. SSH key erstellt 
3. README.md 
4. Github mit SSH verbingun
5. Visual Studio Code Heruntergeladen 
6. Readme datei in repository erstellt 
7. Readmedateis in vscode erstellt 


# Github docs über ssh verbindung

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## neues ssh keys erstellt für mein github account

`ssh -keygen -t ed25519 -C roamn.talakh1234@gmail.com`

keys in /Users/rtalakh/.ssh/ mit bestimmten id erstellt 

## Copy Public Kay

`pbcopy < ~/.ssh/id_ed25519.pub`

kopiere publick key und hinzufüge denn in githab website genau so wie in dockumentation 

## Test SSH verbindung

`ssh -T git@github.com`
 
was ich bekommen:
Hi ProstoboyRoman! You've successfully authenticated, but GitHub does not provide shell access.

## clone Github Repository 

`git clone git@github.com:ProstoboyRoman/Praktikum.git`

