# 🚀 Jenkins: Build, Trigger & Host Webpage (Using Git Clone)

---

> ## 📦 Step 0: Prerequisites
> - Jenkins installed and running  
> - Git installed on the server  
> - A Git repository with a simple web project (HTML / React / Node, etc.)  
> - A web server path available (example: `/var/www/html`)  

---

> ## 📦 Step 1: Open Jenkins
> Open Jenkins in your browser:
>
> ```
> http://<your-server-ip>:8080
> ```
>
> Login to the Jenkins dashboard.

---

> ## 📦 Step 2: Create a New Job
> 1. Click **New Item**  
> 2. Enter a job name (example: `web-build-job`)  
> 3. Select **Freestyle project**  
> 4. Click **OK**

---

> ## 📦 Step 3: Configure Git Repository
> 1. Open the job → Click **Configure**  
> 2. Go to **Source Code Management**  
> 3. Select **Git**  
> 4. In **Repository URL**, paste:
>
> ```
> https://github.com/username/reponame.git
> ```
>
> 5. If the repo is private, add credentials  
> 6. Click **Save**

---

> ## 📦 Step 4: Add Build Script
> 1. Go to job **Configure**  
> 2. Scroll to **Build Steps**  
> 3. Click **Add build step → Execute shell**  
> 4. Add this script:
>
> ```bash
> echo "Starting build process"
> 
> ls -l
> 
> # For Node/React project
> npm install
> npm run build
> 
> echo "Build completed"
> ```
>
> > If it is a simple HTML project, you can skip the `npm` commands.

---

> ## 📦 Step 5: Deploy / Host the Webpage
> Assume your build output is in:
>
> ```
> build/   or   dist/
> ```
>
> Add this **after the build commands** in the same shell step:
>
> ```bash
> echo "Deploying files to web server"
> 
> sudo rm -rf /var/www/html/*
> sudo cp -r build/* /var/www/html/
> ```
>
> (If your folder is `dist/`, use:)
>
> ```bash
> sudo rm -rf /var/www/html/*
> sudo cp -r dist/* /var/www/html/
> ```
>
> Now open in browser:
>
> ```
> http://<your-server-ip>
> ```

---

> ## 📦 Step 6: Trigger the Build (Manual)
> 1. Open your Jenkins job  
> 2. Click **Build Now**  
> 3. Go to **Build History**  
> 4. Click the build number → **Console Output**  
> 5. Check the logs for success or errors  

---

> ## 📦 Step 7: Auto Trigger (Optional)

> ### 🔁 Option A: Poll SCM
> 1. Go to job **Configure**  
> 2. Check **Poll SCM**  
> 3. Add this schedule (every 5 minutes):
>
> ```
> H/5 * * * *
> ```

> ### 🔁 Option B: Git Webhook
> Add this webhook URL in your Git repository:
>
> ```
> http://<your-jenkins-ip>:8080/github-webhook/
> ```
>
> Now every push will trigger a Jenkins build automatically.

---

> ## 📦 Step 8: What This Setup Does
> - Jenkins clones the Git repository  
> - Runs the build script  
> - Generates build output  
> - Copies files to the web server directory  
> - Hosts the webpage  
> - Build can be triggered manually or automatically  

---

> ## 📦 Summary (In My Words)
> - Jenkins is used for automation  
> - Git is used for source code management  
> - Jenkins pulls code from Git  
> - Build script prepares the project  
> - Build output is deployed to server path  
> - Webpage becomes live after every successful build  
