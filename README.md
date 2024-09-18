# Setup pipeline using CircleCI, update GitHub Kubernetes manifest repo and push image on Docker Hub

✨This repository contains the code of the **Kubernetes manifest files** as part of Project 4 of our **10WeeksofCloudOps** series! In this comprehensive hands-on project, we dive deep into the world of **GitOps and ArgoCD**, demonstrating how to implement these essential DevOps practices step by step by **dockerizing** the application and provisioning the infrastructure using **Terraform**.

## 💪Complete Hands-on video tutorial for this project. Click here 👇
[![GitOps , ArgoCD, Terraform](https://i9.ytimg.com/vi_webp/LgBnbmfsIdA/mqdefault.webp?v=65001550&sqp=CMyFgqgG&rs=AOn4CLB-7wLlJjUqu2q7dOdDMdQRyQ46TA)](https://youtu.be/LgBnbmfsIdA "GitOps|ArgoCD|Terraform")

## Architecture

![Architecture Diagram](https://cdn-images-1.medium.com/max/800/1*T5IRoSoiqT8qnYLUprsRUQ.png)


## Synopsis
- When CircleCI notices any changes in the application code, it executes the jobs we have set up. There are a total of four jobs:

### Test: 
- This job tests the code. After the test job is completed, CircleCI proceeds to the next job. 
- Note: I didn't add this job to save time. 

### Build: 
- In the build job, CircleCI pulls the base Docker images and packages our application code inside the image.

### Push: 
- The push job pushes the newly generated images to Docker Hub with a new tag.

### Update Manifest: 
- After completing the push job, the last job is executed, which updates the Kubernetes manifest repository with the new tag. This enables ArgoCD to detect the change and apply it to the cluster.

Following this pipeline ensures that our application code is thoroughly tested, built into Docker images, and deployed with the updated manifest using the GitOps approach.

**This project contains Three GitHub repositories**

➡️ [App Code] (https://github.com/piyushsachdeva/AppCode)

➡️ [Terraform code] (https://github.com/piyushsachdeva/10weeksofcloudops-week4-tf)

➡️ [Manifest Repo] (https://github.com/piyushsachdeva/kube_manifest)

🙏 Thank you so much for reading.
