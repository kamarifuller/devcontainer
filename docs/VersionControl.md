# Source Code Version Control Tools

This repository contains the configuration files for the development environment, the code for our project, as well as our CI/CD pipeline itself. It contains everything needed for development besides our software tools like Docker Desktop and Visual Studio Code. Our benefits come by way of:

- Easy collaboration
- Secure and reliable storage
- History of changes
- Efficient software integration
- Automatian
- Increased feedback

## Version Control

Git was the choice of VCS. It is widely used, has plenty of resources available, and Github specifically has the tools needed readily available.

## Repository Setup

This repository is our one stop shop for development. It contains the container configuration files, our applications code, and the workflows through github. At the root of our repository we have our most important directories 

> Devcontainer configuration files: [.devcontianer](../.devcontainer)

> Dependency and Github Workflow files: [.github](../.github)

> Software application files: [app](../app)

> Documentation on the various tools and code in our repository: [docs](../docs)

> Flutter test application: [test_drive](../test_drive)

> Document with basic repository overview and index: [README.md](../README.md)

## Common Commands and Usage
Clone a repository into a new directory: ```git clone <repository_url>```

Add file(s) to the staging area: ```git add <file1> <file2> ...```

Record changes to the repository: ```git commit -m "Commit message"```

Update remote refs along with associated objects:  
```git push origin <branch_name>```


Show the status of changes in the working directory: ```git status```

List, create, or delete branches respectively:  
```git branch```  
```git branch <branch_name>```  
```git branch -d <branch_name>```

Switch branches or restore working tree files:  
```git checkout <branch_name>```  
```git checkout -b <new_branch_name>```  
```git checkout -- <file>```

Join two or more development histories together:  
```git merge <branch_name>```

Fetch from and integrate with another repository or a local branch:  
```git pull origin <branch_name>```



## Collaboration Features
Having a shared repository allows for anyone with access to get involved in the development process. Because our development environment runs on containers everyone uses the standardized environement. Additionally our VCS logs changes, facilitates branching, and provides conflict resolution tools.

## Challenges and Solutions
See the [project issues](https://github.com/kamarifuller/devcontainer/issues) for ongoing and previous issues as well as possible solutions.

## Conclusion
Ultimately our VCS is our CI/CD pipeline. Not only does it store configuration files for the development environment, the code for our project, as well as our CI/CD pipeline itself. It also has tools conducive to collaboration.