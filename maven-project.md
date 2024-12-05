# Jenkins Lab: Freestyle Project with Maven, Email Notifications, and Artifact Archiving

## Lab Steps

### 1. Configure Global Tools in Jenkins
1. Navigate to `Manage Jenkins > Global Tool Configuration`.
2. Under **Maven**, ensure you have a Maven installation configured. If not:
   - Click **Add Maven**.
   - Provide a name (e.g., `Maven 3.8.6`).
   - Select "Install automatically" and choose the desired version.
   - Click **Save**.

### 2. Create a New Freestyle Project
1. On the Jenkins dashboard, click **New Item**.
2. Enter the project name (e.g., `Maven-Freestyle-Demo`).
3. Select **Freestyle project** and click **OK**.
4. In the project configuration page:
   - Under **Source Code Management**, select **Git**.
   - Enter the repository URL of the Maven project (e.g., `https://github.com/user/maven-sample.git`).
   - If the repository requires authentication, add credentials in Jenkins and select them here.

### 3. Configure the Build Step
1. Scroll to the **Build** section.
2. Click **Add build step** and select **Invoke top-level Maven targets**.
3. Configure the Maven build:
   - Enter `-B -DskipTests clean package` in the **Goals** field.
   - Ensure the correct Maven installation is selected under **Maven Version**.

### 4. Configure Post-Build Actions: Email Notifications
1. Scroll to the **Post-build Actions** section.
2. Click **Add post-build action** and select **Editable Email Notification**.
3. Configure the email settings:
   - Enter a recipient email address in **Project Recipient List** (e.g., `student@example.com`).
   - Optionally, customize the email subject and content template.
   - Ensure **Attach Build Log** is checked if needed.
4. Click **Advanced Settings** to customize further, such as triggers (e.g., for success or failure).

### 5. Configure Post-Build Actions: Archive Artifacts
1. Click **Add post-build action** and select **Archive the artifacts**.
2. Specify the files to archive in the **Files to archive** field:
   - Example: `target/*.jar` to archive all JAR files generated in the `target` directory.
3. Optionally, add patterns to exclude files if needed.

### 6. Save and Build the Project
1. Click **Save** to save the project configuration.
2. On the project page, click **Build Now** to start a build.
3. Monitor the build in the **Build History** section.

---

## Validation
1. Verify the build output:
   - Check the build console logs for Maven build success.
   - Ensure the specified artifacts are archived (visible under the build details).
2. Confirm the email notification:
   - Check the recipient's inbox for build success/failure notifications.
3. Review the archived artifacts:
   - Go to the specific build's details and ensure the artifacts are listed under **Archived Artifacts**.


