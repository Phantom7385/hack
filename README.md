<h1 align="center"> Trojan.C2</h1>
<h4 align="center">Command and Control (C2) Trojan Framework to control, update, and receive data from your implants.</h4>

<h5>Why to use Github to build a trojan framework using Python?</h5>
Because you can use Python's native library import mechanism to deploy new functionality on your trojans. This means you can automatically update your implants, and any dependant libraries, directly from your repo.
In addition, your traffic to GitHub will be encrypted over SSL; several entreprises already use Github for their own work, so your traffic can be completely invisible to their blue teams. 

<br /><br />
<h4>Modules</h4>

This is where you add additional functionality to your trojans.<br />
Each module you add should expose a "run(**args)" function that takes a varialbe number of arguments. 
This enables to load each module in the same fashion, but also allows you to customize the configuration
files to pass different arguments to the modules. 

###### Tip: To assess your modules, push them to GitHub and enable them in a configuration file fror your local testing version of the Trojan. 

<h4>Config</h4>

This folder holds unique config files for each trojan: this is where you tell each trojan which actions to perform and the modules required to do so.<br />
Each trojan should have a unique ID. This help when sorting retrieved data based on the ID and provides modular
control of your trojans. 

<h4>.gitignore</h4>

This file should have the filename of your PAT(personal access token). Give the token read and write permissions.
Create a token [here](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line/)

###### Tip: Create several different tokens for different trojans so you can control what each trojan can access in your repository. That way, if victims catch your trojan, they can’t come along and delete all of your retrieved data.
