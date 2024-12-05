## **Step 1: Create a New Pipeline Job in Jenkins**

1. **Go to Jenkins Dashboard**.

2. **Create a New Job**:
   - Click **New Item**.
   - Enter a name for your pipeline (e.g., `GroovyPipelineFromGitHub`).
   - Select **Pipeline** as the job type and click **OK**.

3. **Configure the Pipeline Job**:
   - In the configuration page, scroll down to the **Pipeline** section.
   - Set **Definition** to **Pipeline script from SCM** (Source Control Management).
   - Set **SCM** to **Git**.
   - In the **Repository URL**, enter the URL of your GitHub repository (e.g., `https://github.com/<your-username>/jenkins-pipeline-demo.git`).

4. **Credentials**:
   - If your repository is private, add your GitHub credentials by clicking **Add** → **Jenkins**, then enter your GitHub username and password or token.

5. **Branch**:
   - By default, Jenkins uses the `master` branch. You can specify another branch if needed.

6. **Script Path**:
   - Ensure that the **Script Path** is set to `Jenkinsfile` (if your file is named something else, specify that here).

7. **Save the Job**.

---

## **Step 2: Build the Pipeline**

1. **Run the Job**:
   - On the job's page, click **Build Now** to trigger the pipeline.

2. **Check Build Progress**:
   - You will see the build in the **Build History** section on the left.
   - Click the build number to view the progress and output.

3. **Console Output**:
   - Check the **Console Output** to see each stage of the pipeline as it executes:
     - Apache (`httpd`) installation.
     - Status check.
     - Success message indicating the website is live.

---


## **Step 3: Modify the Pipeline**

1. **Update Jenkinsfile in GitHub**:
   - You can modify the `Jenkinsfile` in your GitHub repository to add more stages, steps, or logic.

2. **Trigger the Job Automatically**:
   - To automatically trigger the Jenkins job when you push changes to GitHub, you can configure a **Webhook** in GitHub under **Settings** → **Webhooks**.

---

