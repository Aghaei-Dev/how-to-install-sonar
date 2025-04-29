<h3 align='center'>English</h3>

---

### 1. Install Java 17

Download and install the Oracle [Java 17 JDK](https://download.oracle.com/java/17/archive/jdk-17.0.7_windows-x64_bin.msi) for Windows (x64 MSI Installer).

---

### 2. Install SonarQube

Download and install the [SonarQube Community Edition](https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/) for Windows.

---

### 3. Start SonarQube

Unzip the downloaded SonarQube archive, then run the following:

```bash
cd sonar/bin/windows-x86-64
StartSonar.bat
```

---

### 4. Access the SonarQube Dashboard

Open your browser and navigate to:

```
http://localhost:9000
```

**Default login credentials:**

- **Username:** admin  
- **Password:** admin

After logging in, you’ll be prompted to change your password.

---

### 5. Create a Project

- Click **"Create Project"**
- Select **"Manually"**
- Enter your desired **Project Display Name** and **Project Key**
- Save both values — they’ll be needed later
- Choose **"Locally"**
- Generate a **Token**
- Save the token as well (e.g., `sqp_98cd69b25fa89e8133abaa9fd24ff8490d560eda`)

---

### 6. Configure SonarQube in Your Project

#### a. Install the Scanner

```bash
npm i --save-dev sonarqube-scanner
```

#### b. Create Configuration File

In your project root:

- Create a folder named `sonarqube`
- Inside it, create a file named `sonarscan.js`

Add the following content:

```js
const scanner = require('sonarqube-scanner');

scanner(
  {
    serverUrl: 'http://localhost:9000',
    token: 'your_generated_token',
    options: {
      'sonar.projectName': 'Your Project Display Name',
      'sonar.projectDescription': 'Optional project description',
      'sonar.projectKey': 'Your Project Key',
      'sonar.projectVersion': '0.0.1',
      'sonar.exclusions': '',
      'sonar.sourceEncoding': 'UTF-8',
    },
  },
  () => process.exit()
);
```

Replace `'your_generated_token'`, `'Your Project Display Name'`, and `'Your Project Key'` with your actual values.

---

### 7. Run the Scanner

```bash
node ./sonarqube/sonarscan.js
```

Wait for the message:

**"Analysis finished"**

---

### 8. View the Results

Go back to `http://localhost:9000` to see your project dashboard with analysis results.
