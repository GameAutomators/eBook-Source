# Setting up to contribute

1. Fork this repository [GameAutomators/eBook-Source](https://github.com/GameAutomators/eBook-Source) to your profile account
2. `git clone https://github.com/<your github username>/eBook-Source`
3. `git remote add upstream https://github.com/GameAutomators/eBook-Source`
4. `git pull upstream master`

--------------------------------------------------------------------

# Making a contribution

### Note: Never make a contribution from your `master` branch.

1. Before starting to write, ensure that you've done `git pull upstream master` so that you're up to date with the main content.
2. Checkout a new branch, this is like a copy of the content of the book so that you can make changes. `git checkout -b BranchName` where `BranchName` can be anything depending on your contribution. For example, if you're writing an article on arduino you can do `git checkout -b MyArdunioDocument`
3. Once the content is written. Do `git add <filename>` and `git push origin BranchName`
4. Then headover to github and send a pull request.
5. If you want to continue working on the same branch, you can do that or ideally switch back to master by doing `git checkout master`
6. Pull back from `upstream` by doing `step 1` before starting to make the next contribution to the book.