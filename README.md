# My React Web Application

Welcome to my awesome React web application! This document provides a deeper insight into how the application works and its various components.

## File Structure

The project is organized into the following directories and files:

- `.github/`: Contains GitHub Actions workflows for CI/CD.
- `kubernetes/`: Holds Kubernetes deployment configuration.
- `src/`: Contains the source code for the React application.
  - `components/`: Subdirectory for React components.
  - `App.js`: Main React component responsible for rendering the application.
  - `App.css`: Stylesheet for the application.
- `Dockerfile`: Dockerfile for containerizing the React application.
- `package.json`: Node.js package configuration file.
- `README.md`: README file providing instructions and information about the project.

## Dockerfile

The Dockerfile defines how the React application is containerized. It uses a multi-stage build process:
1. **Stage 1 - Build React Application**: Installs dependencies, builds the React app, and creates a production build.
2. **Stage 2 - Serve React Application**: Copies the production build into an Nginx container to serve the application.

## Kubernetes Deployment Configuration (kubernetes/deployment.yaml)

The Kubernetes deployment configuration defines how the application is deployed on a Kubernetes cluster:
- **Deployment**: Specifies the number of replicas and container image to use.
- **Service**: Exposes the deployment internally within the cluster.
- **Ingress**: Routes external traffic to the service based on the specified host.

## GitHub Actions Workflow (`.github/workflows/main.yml`)

The GitHub Actions workflow automates the CI/CD pipeline:
- **on**: Triggers the pipeline on pushes to the `main` branch.
- **jobs**: Defines a single job named `build-and-deploy`.
  - **runs-on**: Specifies the execution environment for the job.
  - **steps**: Contains the sequence of steps to be executed:
    - **Checkout code**: Fetches the repository's code.
    - **Build Docker image**: Builds the Docker image for the React app.
    - **Push Docker image to registry**: Tags and pushes the Docker image to a container registry.
    - **Deploy to Kubernetes**: Applies the Kubernetes deployment configuration.

## React Components (src/components/App.js)

The main React component, `App.js`, is responsible for rendering the application. It includes the following key features:
- **Theme Selector**: Allows users to toggle between different themes (light, dark, blue, green).
- **State Management**: Uses React hooks (`useState`) to manage the current theme.

## Styling (src/App.css)

The CSS file (`App.css`) defines styles for the application, including themes and component styles. It provides visual consistency and enhances the user experience.

## Package Configuration (package.json)

The `package.json` file specifies dependencies, scripts, and other project metadata required for building and running the application.

## README.md

The README file provides instructions on how to clone, install dependencies, and run the application. It also includes information about available themes and serves as a guide for users and contributors.

