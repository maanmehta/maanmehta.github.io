# Basic GitHub Branch Management
## How to create and merge Github branches using Android Studio

### About this tutorial

It is an established best practice not to directly make code changes on the master branch. This holds true, even if you are the only developer working on the project. When you want to make some code changes, you should create a new "work" branch from your `master` branch, make your code changes to the new `work` branch, complete your testing and when you are done, merge changes in your `work` branch to the `master` branch and now you can safely delete your work branch.

This tutorial gives step-by-step instructions on how to do basic Github branch management from Android Studio. I will cover the following topics:

1. Create a new `work` branch from `master` branch
2. Make code changes on `work` branch, commit and push your commits to the Github server
3. Switch between your branches and see that you get different codebase in Android Studio
4. Merge your `work` branch to `master` branch and push your changes (the merge) to the Github server
5. Delete your both `work` branches - local and remote

# 1. Create a new `work` branch from `master` branch

## Android Studio

- From the status bar at the bottom of Android Studio, click **Git:master** and then click **New Branch**
- Enter `work` as the name of the new branch and click **OK**


![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/newbranch01.png)

<br>
<br>

![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/newbranch02.png)

<br>
<br>

This will create a new local `work` branch and switch your Android Studio to this new local branch as you can see in the screenshot below:

<br>
<br>

![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/newbranch03.png)

<br>
<br>

In the background, Android Studio used Git to created a new local `work` branch using the code snapshot from the local `master` branch and automatically checks out the new local `work` branch ready for you to start making code changes in Android Studio.

But, this new branch does not yet exist on the remote Github server. In other words, we now have a Local Branch called `work` but there is no "Remote Branch" called `work` yet on the Github server. In order to do that, we need to **Push** our local changes to the server. Execute the Git Push** for the changes (new work branch) to be replicated to the (Github) server. That will push the local `work` branch to a new remote `work` branch on the server.

![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/pushedNewWorkBranch.png)

After the **Push**, you can browse the codebase of the new remote `work` branch on the Github website as follows:
- Logon to Github website
- Browse to your repository.
    - Your repository dashboard on Github website will show the number of branches in your repository and in this case and as shown in the screenshot below it should be **2 Branches**<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/2Branches.png)<br><br>
    - Click on **2 Branches** and then click **All Branches** to view your branches<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/allBranches.png)<br><br>

# 2. Make code changes on local `work` branch, commit your changes and push your commits to the (Github) server

Now, while you are using the local `work` branch, make some code changes and Commit and **Push** to the (Github) server. Note that unless you *Push*, your changes will remain in your local branch and will not be copied (pushed) to the remote `work` branch on the Github server.

### Verify that your changes have been pushed to the remote `work` branch on the Github server

- Login to Github website and browse to your repository and you will find that your new code changes are not there in the default `master` branch. This is correct because we made changes and did a Commit and **Push** but we did this in the `work` branch. So, these changes should not be in the `master` branch but actually in the `work` branch.
- Switch to the new `work` branch on the Github website and viola, your changes are there.

<br>
<br>

![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/switchToWork01.png)

<br>
<br>

# 3. Switch between your branches and see that you get different codebase in Android Studio

- Switch between your remote branches on the Github website and you will notice the differences in the code base between the `work` and the `master` branch.
- You can do the same for local branches on Android Studio as follows
    - Switch your active branch on Android Studio back to your local `master` branch - From the status bar, click on **Git:work** which is your current branch in Android Studio, and select **master -> origin/master** under the **Local Branches** section and click **Checkout**. You can now verify that the code base in Android Studio shows your code that was in local `master` branch and does not have the changes you made and commited to the local `work` branch.<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/checkoutMaster01.png)<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/checkedoutMaster01.png)<br><br>
    - Now, switch back to the local `work` branch on Android Studio - From the status bar, click on **Git:master** which is your current branch in Android Studio, and select **work -> origin/work** under the **Local Branches** section and click **Checkout**. You can now verify that the code base in Android Studio shows your code that is in the `work` branch and has all the changes you made and commited to the `work` branch.<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/checkoutWork01.png)<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/checkedoutWork01.png)<br><br>

# 4. Merge your local `work` branch to local `master` branch and push your changes (the merge) to the remote `master` branch on the server

When you want to merge your code changes from branch B to branch A, you have to switch (checkout) to branch A and then execute the merge command and select Branch B. Git will then marge the current codebase of the Branch B to Branch A. And now, the codebase of branches A and B will be same. Keep in mind, at this point, all of this merge has been done to your branches A and B that are local to your computer and has not been pushed to their corresponding remote branches on the Github server. Therefore, you will need to execute a Git Push from your local computer (e.g. your Android Studio). Here are the steps that you can execute to merge all the commits you have made on your `work` branch to the `master` branch:

- Switch your branches on the Github website and you will notice the differences in the code base between the `work` and the `master` branch.
- You can do the same on Android Studio as follows:
    - Switch your active branch on Android Studio back to the local `master` branch - From the status bar, click on **Git:work** which is your current branch in Android Studio, and select **master -> origin/master** under the **Local Branches** section and click **Checkout**
    - Now execute merge of `work` branch to the `master` branch as follows - From the status bar, click on **Git:master** which is your current branch in Android Studio, and select **work -> origin/work** under the **Local Branches** section and click **Merge**<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/merge01.png)<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/mergedWorkToMaster01.png)<br><br>
    - At this point, even though it seems that your merge has been completed, but it has only been completed on your local branches and has not been pushed to the remote branches on the Github server. You can verify this by checking on the Github website and you will notice that indeed the changes from the `work` branch have not been reflected on the remote `master` branch on the server.
    - Execute `Push` to merge your changes to the Github server

# 5. Delete both local and remote `work` branches

Usually once a working branch is merged with the `master` branch and changes pushed to the remote `master` branch, the purpose of the `work` branch is done and we should delete it. One thing we need to be remember is that for branch deletion, we need to separately delete both local and remote copies of the `work` branch. We cannot just simply delete the local `work` branch and then expect that remote branch will be delete by a Git Push. We have to delete both local and remote branches as two seperate steps as follows:

- Delete local `work' branch as follows:
    - Either click on **Delete work** link in the *merge* confirmation message<br>
        ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/mergedWorkToMaster01.png)<br><br>

    - OR, from the status bar, click on **Git:master** which is your current branch in Android Studio, and then under the **Local Branches**, select **work -> origin/work** and click **Delete**. This will delete the "local" `work` branch only and not the "remote" `work` branch on the Github server<br><br>
        ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/deleteLocalWork.png)<br><br>

- Delete the remote `work` branch as follows:
    - Using Android Studio - From the status bar, click on **Git:master** which is your current branch in Android Studio, and then under the **Remote Branches**, select **origin/work** and click **Delete**. This will delete the remote `work` branch from the Github server<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/deleteWorkRemote.png)<br><br>
    ![Current Weather](https://raw.githubusercontent.com/maanmehta/screenshots/master/branches/remoteWorkBranchDeleted.png)<br><br>

    - Or using Github website - Browse to your repository on Github website and select the appropriate remote branch to delete
