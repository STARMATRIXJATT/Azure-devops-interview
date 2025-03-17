# Azure-devops-interview
1️⃣ What is the difference between a Build Pipeline and a Release Pipeline in Azure DevOps?
Answer:

Build Pipeline (CI): Automates the process of code compilation, running unit tests, and creating build artifacts.
Release Pipeline (CD): Focuses on deploying those build artifacts to various environments (Dev, QA, Prod) and executing post-deployment tasks like approvals, integration tests, etc.
2️⃣ How do you manage multi-stage YAML pipelines in Azure DevOps?
Answer:

Use YAML files to define multiple stages like build, test, deploy.
Each stage can have jobs and steps with conditions, approvals, or dependencies.
Improves pipeline-as-code (PaC) practices and versioning with the repository.
3️⃣ How do you handle secrets in YAML pipelines vs Classic pipelines?
Answer:

YAML Pipelines: Use variable groups linked to Azure Key Vault or pipeline-level secrets.
Classic Pipelines: Use library variable groups or link directly to Key Vault.
In both, avoid plain text values and leverage service connections with minimal privileges.
4️⃣ Explain the difference between Microsoft-hosted agents and self-hosted agents. When would you choose each?
Answer:

Microsoft-hosted agents: Pre-configured, easy to set up, maintained by Microsoft, but limited customization.
Self-hosted agents: Custom environments, more control over tools/dependencies, useful when specific OS versions, libraries, or security policies are required.
5️⃣ How do you ensure zero-downtime deployment with Azure DevOps Pipelines?
Answer:

Implement Blue-Green or Canary deployments.
Use deployment slots (e.g., in Azure App Service) to deploy to a staging slot and swap after validation.
Combine with health probes and traffic routing for gradual rollout.
6️⃣ How would you integrate SonarQube or other static code analysis tools into Azure DevOps Pipelines?
Answer:

Use the SonarQube Azure DevOps extension.
Add tasks in your pipeline YAML to run SonarQube scans during CI.
Configure quality gates in SonarQube to fail the pipeline if code quality metrics aren’t met.
7️⃣ Explain how Azure DevOps handles pipeline artifacts and what options you have for storing them.
Answer:

Artifacts are build outputs (e.g., binaries, Docker images).
Azure DevOps stores artifacts in the built-in artifact storage, Azure Artifacts, or external storages like Azure Blob Storage or ACR.
8️⃣ How would you configure approvals and gates in Azure Pipelines?
Answer:

Configure pre-deployment and post-deployment approvals on stages or environments.
Gates can include Azure Monitor alerts, work item queries, or custom REST APIs to verify conditions before promoting to production.
9️⃣ How do you set up pipeline caching in Azure DevOps? Why is it important?
Answer:

Use task: Cache@2 in YAML pipelines to cache dependencies like npm, Maven, or pip.
Reduces pipeline execution time by reusing previously downloaded packages/artifacts.
🔟 How do you integrate Azure Boards with Azure Pipelines?
Answer:

Link Azure Boards work items (e.g., user stories, bugs) to pipeline commits or pull requests.
Enable automatic updates of work item states based on pipeline progress or completion.
