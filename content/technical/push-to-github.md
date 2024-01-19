+++
title = 'Push to Github'
date = 2024-01-19T19:04:00+05:30
draft = false
description = 'Push to github using Http or SSH connection'
category= ["technical"]
tags= ["technical-post","github","ssh" , "2" , "https" ,"git"]
+++


Hello all, this is gonna be my first technical post/blog which is on a unique problem I faced while deploying this website code on github.

##### How can we post/push our work from a single system/pc as two different users on local to two different Github account?

Let me explain what i meant by this, so while i was making this blog site ,I wanted it to be push on my new anonymous github account instead of my personal github account(having my personal details) ,this meant having 2 local users too for two different repository to push on Git too.

So how do we go forward with it , after googling a lot and spending some time on different articles, I found one approach of using two different git config file ,one global user config file defined with my personal Github user detail and second local user gitconfig file defined at a path directory of the special repository that need to be pushed on my anonymous Github account .
link for the article I referred for this approach:
[Here](https://dev.to/equiman/how-to-use-multiple-users-with-git-2e9l)

But I individually faced difficulty with this method as I couldn't make it to work on my system.The problem I faced was when Git tried to make connection with Github using `HTTPS` approach which usually for single Github account every one uses, the credential of Github user account are stored in Credential Manager in Settings. (talking about Windows as I use that only.)
And it can't store more than 1 account detail for a Github user so at the end it give permission /access denied while pushing the code.

So what if there is another method to HTTPS to connect to Github i.e using the `SSH (Secure Shell protocol)`.
yup, SSH comes to your rescue.

So SSH uses private key and public key to encrypt your data(in our case our repository changes) and communicates over the unseured network in a secure way i.e to Github. 
The public key generated using SSH should be put to store as a new environment variable at your Github setting ,whenever you connect using SSH to Github from local system , it verifies the user account signature while push code to your Github repository from your system.

I confess , I was not a fan of SSH connnection before to connect to Github due to use of terminal commands and keys as I used to get confused before and forget about keys and stuff. But now after giving it a go and putting my head , I like it. So towards positive progress.
Link to [How to use SSH connection to Github](https://www.warp.dev/terminus/git-clone-ssh)

Bottomline : To push/connect code to two different user git account from local on a single system/pc to two different Github user profile  , one can use Https connection for one user profile and another SSH for another user profile.It will work smoothly for both account simultaneously from a single pc.

Happy friday!! Hope you like this and you learned a new thing.


