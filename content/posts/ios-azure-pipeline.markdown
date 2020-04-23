---
title: "iOS Azure Pipeline"
date: 2020-04-23T15:47:40+02:00
draft: false
---

I got the task of setting up a build pipeline for an iOS project using Azure DevOps. By following the documentation, this was easy to set up a dummy project without any dependencies. If you are using CocoaPod or Carthage for dependency management, you'll find tasks that support this out of the box. 

We have moved away from CocoaPods and Carthage, and are now using SPM, the Swift Package Manager. I did not expect that to be an issue since this now is part of Xcode, but I was wrong.

When running the pipeline, I got this error 

```
/usr/bin/xcodebuild failed with return code: 74 
xcodebuild: error: Could not resolve package dependencies: 
 The server SSH fingerprint failed to verify
```

The solution that worked out for me was to add the [Install SSH Key task](https://docs.microsoft.com/en-us/azure/devops/pipelines/tasks/utility/install-ssh-key?view=azure-devops), and follow the documentation found there.

The documentation tells us: _Select the SSH key that was uploaded to Secure Files to install on the agent_

You will find a tab under Library with the label *Secure files*. There you upload the private key, generated earlier. 


The task that I added looks like this:
```
- task: InstallSSHKey@0
  inputs:
    knownHostsEntry: 'github.com,140.xxx.xxx.x ssh-rsa AAAAB3....=='
    sshPublicKey: 'ssh-rsa AA...'
    sshPassphrase: '...'
    sshKeySecureFile: 'Your secure file added to Secure Files, under Libraries'    
```    