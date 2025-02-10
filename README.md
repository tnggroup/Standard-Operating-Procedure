
**Version:** 1.0  

**Date:** 05/02/2025

**Created By:** [Bhakti N](https://github.com/bhakti-n)

**Reviewed By:**  TBD

**Approved By:** TBD


This has all the steps and best practices outlined for using Github version control, to collaborate and manage your project scripts within TNG. 

This covers Repository Setup, workflows, issue management, pull requests, code reviews, and branching strategies. Please feel free to click on skip forward to the parts that are most relevant to you.

To begin with some housekeeping:
- **Repository**: A project or storage space for code, files, and version history.
- **Branch**: A separate line of development in Git used to isolate work on specific features, fixes, or experiments.
- **Pull Request (PR)**: A request to merge changes from one branch to another, typically used for reviewing and discussing code before it is merged into the main codebase.
- **Fork**: A personal copy of a repository that allows you to freely experiment with changes without affecting the original project. When you fork a repository, you create a separate version of that repository under your account where you have full control to make changes without affecting the original repository (often called the "upstream" repository).
- **Issue**: A GitHub tool for tracking bugs, features, or tasks related to a project.

## Repository Setup
### 1. Create a repository 
- Click on the **+** icon in the top right corner and select **New repository**.
![Pasted image 20250131163729](https://github.com/user-attachments/assets/fdad2907-6737-416a-84a0-f83067cae77b)

- Fill in the repository name, description, and visibility (public or private).
![Pasted image 20250131163749](https://github.com/user-attachments/assets/f7415a78-62f5-4469-acd9-965f8af3dd15)

- The best practice is to always initialize with a README.md (such as this one!) and choose a license if applicable.

### 2. Cloning a Repository 
If you have created your repository and would like to clone to your virtual environment
`git clone https://github.com/<YOUR-username>/<repository-name>.git`

### 3. Set Up Branch Protection (for main/master branch):
Branch protection rules help safeguard the `main` or `master` branch, ensuring that changes undergo a proper review process before they are integrated. This is crucial for maintaining code quality and stability in production environments
- In the repository's settings, go to **Branches**.
- Add a branch protection rule for `main` (or `master`) to prevent direct commits and ensure pull requests are used for all changes.
![Pasted image 20250205143811](https://github.com/user-attachments/assets/2a16a960-b68e-4421-926e-6b477bf18d5b)


### 4. Forking a Repository 
Fork the repository by clicking the **Fork** button on the top right of the repository page.
![Pasted image 20250205161236](https://github.com/user-attachments/assets/f2f8bf35-fc38-49b8-b1ac-d0d1668c0a4b)
Then clone the repository (2) to your local machine.

> [!Keeping your fork up-to date]
> 1. **Add the Upstream Remote:** To keep your fork up to date with the original repository, add the original repository as a remote called "upstream."
> `git remote add upstream https://github.com/original-owner/repository-name.git`
> 2. Fetch and merge changes from upstream:
> `git fetch upstream git checkout main git merge upstream/main`
> 1. **Rebasing Your Branch**:  
> `git fetch origin git rebase origin/main`


### 6. Commit(s) and Pushing Changes
When you make changes to the code you will utilize commits and pushing changes. Always add additional meaningful information to your commits as it can be helpful during reviews and for future reference.

	1. `git add .`
	2. `git commit -m "Added new feature X"`

> [!NOTE] Commit Message Guide
> Use clear, concise commit messages that describe the change made. Follow the format:
> 
>`<type>: <short description of the change>  Example: feat: add new login page fix: correct bug with form validation`


	3. `git push origin feature/branch-name`


### 7. Pull Requests
Go to the repository on GitHub and click **New Pull Request**. Select the source branch (your feature branch) and the destination branch (usually `main`).
![Pasted image 20250205165351](https://github.com/user-attachments/assets/2710e416-035e-4cc3-a8f6-332006d1c3c1)



## Code Review and Merges
Assigned Reviewers for TNG : 

3. For any changes suggested not by owners of the repository, comments will be left on sections of the code asking for clarification (to be provided in the comments) or to suggest improvements.
4. Post-Approval: the pull request can be merged through either
	1. **Squash and Merge**: Combines all commits into one for a cleaner history.
    2. **Merge Commit**: Keeps all individual commits from the feature branch.
    3. **Rebase and Merge**: Rewrites history and applies the feature branch commits onto the `main` branch.
5. **After your merge please remember to clean the feature branch to keep the repository clean and organized.**

## Standard Readme.md template for repositories
To maintain consistency and readability please use the following Readme.md on your repositories, and do try to keep them constantly updated if and when possible.

> [!Sample template]
> #### Project Name
> 
> ##### Description
> Briefly describe what this project does and who it's for. Provide context and add a link to any live demo or product if applicable.
> 
> ##### Installation
> Provide detailed step-by-step instructions on how to set up the project locally. This could include prerequisites, environment setup, and any other dependencies.
> 
> 
> `git clone https://yourproject/repository.git`
> `cd repository`
> `pip install -r requirements.txt #to install dependencies`
> `follow this with installation commands or python your_script.py`







---

### **Troubleshooting**

- **Merge Conflicts**: If a merge conflict occurs, resolve it by reviewing the conflicting files and deciding on the appropriate changes.


---

### **Additional Resources**

- GitHub Documentation: [https://docs.github.com](https://docs.github.com)
- GitHub Guides: [https://guides.github.com](https://guides.github.com)
- Git Flow Workflow: https://nvie.com/posts/a-successful-git-branching-model/

---

### **Approval and Revision History**

- **Version 1.0** – [05/02/2025] – Initial SOP creation
