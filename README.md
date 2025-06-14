<!-- Improved compatibility of back to top link -->
<a id="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="logo.jpg" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Asian Food</h3>

  <p align="center">
    A simple 3 tier web app to show the asian food restaurant's menu. 
    <br />
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <!-- <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul> -->
    </li>
    <li>
      <a href="#project-structure">Project Structure</a>
      <!-- <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul> -->
    </li>
    <li><a href="#branch-strategy">Branch Strategy</a></li>
    <li><a href="#environment">Environment</a></li>
    <li><a href="#tools-and-technologies">Tools and Technologies</a></li>
    <li><a href="#repositories">Repositories</a></li>
    <li><a href="#how-to-try-this-project">How to Try This Project</a></li>
    <li><a href="#what-i-learned">What I learned</a></li>
    <li><a href="#plan-to-improve-this-project">Plan to improve this project</a></li>
  </ol>
</details>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## About The Project

Asian food is the 3 tier web app that show user the asian food restaurant's menu. 

- Presentation Layer (Frontend): To show the UI of the app
- Application Layer (Backend): To create api endpoint and send menu detail to frontend.
- Data Layer (Database): Store menu detail
- We use Azure Kubernetes Service (AKS) to run containers

Developers can just use **docker compose** to run the app locally without any infrastructure.

[Demo]()

### Example
<img src="asian-food-fullpage.jpeg" width="250"/>
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Project Structure

<img src="diagram-export-5-24-2025-6_46_39-PM.png" width="500"/>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Branch Strategy

- main: The main branch
- release: The branch for release
- dev: The branch for development
- feature: The branch for feature development
- hotfix: The branch for hotfix development

<img src="gitflow.png" width="450" alt="gitflow"/>
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Environment

- **Testing** : The environment for testing the app, the data is not saved. Tester can use this environment to test the app with their own data.
- **Staging**: The environment for staging the app, stakeholder can use this environment to test the app with the real data before deploying to production or make the adjustment to the app.
- **Production**: The environment for production the app with the real data and it is accessible to the public.
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Tools and Technologies

1. **Terraform (IaC)**: To deploy Azure Infrastructure resources using Terraform modules.
2. **Ansible (IaC)**: To provision VM Instances for AKS worker node.
3. **Azure Resources**:
    * AKS: Kubernetes on Azure
4. **Docker**: To dockerize my ReactJs application using a Dockerfile.
5. **Kubernetes (k8s)**: To orchestrate the docker container.
6. **Azure DevOps**: To do these Jobs on every git push command, also manually triggered:
    * Automate the Infrastructure building and destroying process.
    * Provision the VM Instances (Install and configure Docker).
    * Build, push docker image to Docker Hub, then pull and run docker container in the AKS instance.
7. **Prometheus & Grafana**: Monitor the resource of pods in AKS.
8. **ArgoCD (GitOps)**: Automate the deployment when the configs are changed.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Repositories

Frontend: [asian-food-frontend](https://github.com/cheulong/asian-food-frontend)

Backend: [asian-food-backend](https://github.com/cheulong/asian-food-backend)

Infrastructure: [asian-food-infra](https://github.com/cheulong/asian-food-infra)

Deployment: [asian-food-deployment](https://github.com/cheulong/asian-food-deployment)
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## How to Try This Project:

This project is easy to start locally with out any infrastructure.

### Prerequisites

Your machine must have the following tools installed:
* git
* docker

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/cheulong/asian-food-frontend
   git clone https://github.com/cheulong/asian-food-backend
   ```
2. Start the app
   ```sh
   cd asian-food-frontend
   docker compose up
   ```
   ```sh
   cd asian-food-backend
   docker compose up
   ```

4. Delete the app
   ```sh
   cd asian-food-frontend
   docker compose down --rmi local -v
   ```
    ```sh
   cd asian-food-frontend
   docker-compose down --rmi local -v
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## What I learned

1. How to use **Azure DevOps** to do these Jobs on every git push command, also manually triggered:
    * Automate the Infrastructure building and destroying process.
    * Provision the VM Instances (Install and configure Docker).
    * Build, push docker image to Docker Hub, then pull and run docker container in the AKS instance.
2. How to use **docker compose** to run the app locally without any infrastructure.
2. How to deploy the app on **Azure Kubernetes Service (AKS)**.
3. How to use **ArgoCD (GitOps)** to automate the deployment when the configs are changed.
4. How to use **Prometheus & Grafana** to monitor the resource of pods in AKS.
5. How to use **Terraform (IaC)** to deploy Azure Infrastructure resources using Terraform modules.
6. How to provision VM Instances for AKS worker node.
7. Implement branch strategy to manage the code.

<!-- ## Release History
* 0.2.1
    * CHANGE: Update docs (module code remains unchanged)
* 0.2.0 -->

## Plan to improve this project
- [ ] Send email to admin when the app is deployed
- [ ] Add more menu item
- [ ] Add admin dashboard to add/remove menu item
- [ ] Change the UI of the app to show the image of the menu item

<p align="right">(<a href="#readme-top">back to top</a>)</p>
