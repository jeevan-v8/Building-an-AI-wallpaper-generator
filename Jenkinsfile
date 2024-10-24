groovy
Copy code
pipeline {
agent any
tools {
nodejs &#39;NodeJS&#39; // Name of your NodeJS installation in Jenkins
}
stages {
stage(&#39;Checkout&#39;) {
steps {
// Checkout the code from GitHub
git url: &#39;https://github.com/your-repo/your-project.git&#39;,
branch: &#39;main&#39;
}
}
stage(&#39;Install Dependencies&#39;) {
steps {
// Install Node.js dependencies
sh &#39;npm install&#39;
}
}
stage(&#39;Build with Maven&#39;) {

steps {
// Build the application using Maven
sh &#39;mvn clean package&#39;
}
}
stage(&#39;Run Selenium Tests&#39;) {
steps {
// Run Selenium tests (this assumes you have a script for
running your tests)
// You may need to adjust this command based on your test
setup
sh &#39;mvn test -Dtest=YourSeleniumTestClass&#39;
}
}
}
post {
success {
echo &#39;Build and tests were successful!&#39;
}
failure {
echo &#39;Build or tests failed!&#39;
}
always {
// Clean up or send notifications
echo &#39;Cleaning up...&#39;
}
}
}