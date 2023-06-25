<h3 align='center'>English</h3>

---

Download and Install Oracle [Java 17](https://download.oracle.com/java/17/archive/jdk-17.0.7_windows-x64_bin.msi 'sha256 ') on Windows

Download and Install [SonarQube](https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/) on Windows

Start SonarQube on Windows

- unzip sonar

```
cd sonar/bin/windows-x86-64
run StartSonar.bat

```

Access SonarQube on Windows

```
localhost:9000 OR IP:9000
```

SonarQube default username and password

- login: admin
- password: admin

once login it will ask to change password, update you password as your requirement.

once password updated, you will navigate to SonarQube Dashboard .

then

- create project

then

- manually

after that

- chose Project display name and Project key

so

- locally

generate a token

(something like this : sqp_98cd69b25fa89e8133abaa9fd24ff8490d560eda)

```
cd project folder
```

---

install sonar using terminal

```
npm i --dev sonarqube-scanner
```

in the root of your project create **sonarqube** folder and **sonarscan.js** file

in the **sonarscan.js** write these lines of code

```
const scanner = require('sonarqube-scanner');
scanner(
{
serverUrl: 'http://localhost:9000',
token: "",
options: {
'sonar.projectName': 'Project display name ",
'sonar.projectDescription': 'Here I can add a description of my project',
'sonar.projectKey': 'Project key ',
'sonar.projectVersion': '0.0.1',
'sonar.exclusions': '',
'sonar.sourceEncoding': 'UTF-8',
}
},
() => process.exit()
)
```

In terminal exe this

```
node ./sonarqube/sonarscan.js
```

wait until see this

**Analyses finished**

now head back to localhost 9000 and we are in the dashboard

you can see all of information about your project like bugs and ...

<br/>
<br/>
<br/>

<div dir="rtl">

<h3 align='center'>فارسی</h3>

---

دانلود ونصب [JDK](https://download.oracle.com/java/17/archive/jdk-17.0.7_windows-x64_bin.msi 'sha256 ') نسخه ( Windows x64 MSI Installer )

دانلود و نصب [SonarQube](https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/) نسخه ( Community Edition )

سونار را از زیپ در میاوریم و واردش میشویم
وارد bin میشیم
وارد windows-x86-64 میشیم
فایل StartSonar.bat را ران میکنیم

حالا رو پورت http://localhost:9000 سونار رو داریم

لاگین میکنیم :
بار اول به صورت پیشفرض
login: admin
password: admin

رمز را عوض میکینم و دوباره لاگین میکنیم

دکمه create project -> manually

Project display name و Project key رو دلخواه انتخاب میکنیم
**ولی یه جا باس نگهداریمش ک نیازش داریم**

حالا دکمه locally

یک توکن میسازیم **و باز هم نگهداریش میکنیم**
(یک چنین چیزیه sqp_98cd69b25fa89e8133abaa9fd24ff8490d560eda)

کارمون اینجا تموم میشه و میریم داخل پروژه

---

داخل ترمینال با استفاده از سونار را نصب میکنیم

```
npm i --dev sonarqube-scanner
```

داخل روت پروژه فولدر sonarqube رو اضافه و داخلش فایل sonarscan.js رو اضافه میکنیم

داخل فایل sonarscan.js دستور زیر را مینویسیم

---

<div dir="ltr">

const scanner = require('sonarqube-scanner');
scanner(
{
serverUrl: 'http://localhost:9000',
token: "همان توکنی ک ساختیم را اینجا ",
options: {
'sonar.projectName': 'Project display name مرحله 8",
'sonar.projectDescription': 'Here I can add a description of my project',
'sonar.projectKey': 'Project key مرحله 8',
'sonar.projectVersion': '0.0.1',
'sonar.exclusions': '',
'sonar.sourceEncoding': 'UTF-8',
}
},
() => process.exit()
)

</div>

---

داخل ترمینال دستور را اجرا میکنیم

```
node ./sonarqube/sonarscan.js
```

منتظر میمونیم تا بنویسه
**analyses finished**

حالا دوباره وارد همان لوکال هاست 9000 میشویم و داخل دشبورد اطلاعات پروژه و باگ ها و غیره قابل مشاهده است

</div>
