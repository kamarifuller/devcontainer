# CI/CD Pipeline Documentation

## CI/CD Pipeline Environment

### Infrastructure and Environment Overview
Our CI/CD pipeline operates within a containerized environment utilizing Docker containers for consistent and reproducible builds. The primary operating system utilized within these containers is **Ubuntu (jammy)**, providing a stable and widely supported base for our development processes. We leverage cloud services for version control and continuous integration, particularly **GitHub** for version control and **GitHub Actions** for automation.

### Key Components:
- **Base Image:** Ubuntu (jammy)
- **Cloud Services:** GitHub for version control and GitHub Actions for CI/CD automation
- **Containerization:** Docker for creating and managing lightweight containers
- **Language Support:** Dart and Flutter for application development
- **IDE Integration:** Visual Studio Code with Dev Containers for seamless development experience

## CI/CD Pipeline Tools

### GitHub Actions

**Selection Rationale:** GitHub Actions was chosen for its seamless integration with our version control platform GitHub. It provides robust CI/CD capabilities and allows us to define workflows using YAML syntax directly within our repository.

### Features:

- Tight integration with GitHub repositories, making it easy to set up and manage CI/CD workflows.
- Supports a wide range of programming languages and frameworks, including Flutter.
- Provides a rich ecosystem of community-created actions for extending functionality.

### Limitations:

- YAML-based configuration can become complex for more intricate workflows.
- Relatively new compared to established CI/CD platforms like Jenkins.

## Automation Process

### Workflow Overview

Our CI/CD pipeline automates the build and deployment phases of our Flutter web application. The process encompasses code compilation, testing, and deployment to production or staging environments.

### Workflow Implementation:
1. **Trigger:** The workflow is triggered on pushes to the main branch.
2. **Setup Environment:** Sets up the environment with necessary dependencies and tools, including Flutter.
3. **Build and Test:** Compiles the Flutter application and executes unit tests.
4. **Artifact Generation:** Generates artifacts such as compiled code and test reports.
5. **Deployment:** Deploys the application, in this case, to GitHub Pages for hosting.

### Workflow Challenges

- **Build Failures:** Occasional build failures were encountered, primarily due to environmental factors. Solutions include ensuring proper dependencies are installed and updated.
- **Incorrect Paths:** Using bash commands like ``pwd`` or ``ls -R``
helps in knowing where files are located on the runner
- **Missing Files:** Files are not automatically shared between jobs. Artifacts may be used to do so, however, artifacts cannot be shared between seperate workflows.
