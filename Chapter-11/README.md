# Integrating JMeter with CI/CD Pipelines

- This chapter covers the basics of running JMeter tests in CLI mode for automation and introduces integration of JMeter with Jenkins or other CI/CD tools to include performance testing in continuous delivery workflows.

## Table of Contents

- [Section 1: Running JMeter Tests in CLI Mode for Automation](#section-1-running-jmeter-tests-in-cli-mode-for-automation)

- [Section 2: Integrating JMeter with Jenkins or Other CI Tools](#section-2-integrating-jmeter-with-jenkins-or-other-ci-tools)

- [Summary](#summary)

## Section 1: Running JMeter Tests in CLI Mode for Automation

- JMeter tests can be executed in CLI (Command Line Interface) mode, which is essential for automation within CI/CD pipelines. 

- Running tests in CLI mode allows tests to run without a graphical interface, making it ideal for automated environments.

- Steps to Run JMeter in CLI Mode:

    1. Open a terminal or command prompt.
    
    2. Navigate to the JMeter bin directory.
    
    3. Use the following command format to run your test:

        ```  
        jmeter -n -t <test-plan.jmx> -l <result-file.jtl> -e -o <report-output-folder>
        ```

        - **-n**: Non-GUI mode.
        
        - **-t**: Specifies the test plan file.
        
        - **-l**: Specifies the log file where results will be stored.
        
        - **-e**: Enables generating the HTML dashboard.
        
        - **-o**: Specifies the folder for output reports.
        
- Automating the execution of JMeter tests in CLI mode is a critical step toward integrating performance testing into your CI/CD pipeline.

## Section 2: Integrating JMeter with Jenkins or Other CI Tools

- Integrating JMeter with CI/CD tools like Jenkins ensures that performance tests are run automatically as part of the software delivery process. 
 
- This helps catch performance regressions early in the development lifecycle.

- Basic Integration Steps with Jenkins:

    1. Install JMeter on the same machine where Jenkins is running, or ensure JMeter is accessible in the build environment.
    
    2. Set up a Jenkins job to run JMeter tests:
    
        - In the Jenkins job configuration, under the Build section, add an Execute shell or Execute Windows batch command step.
        
        - Use the same CLI command from section 11.1 to execute the JMeter test.

    3. Add a post-build step to publish JMeter results:
        
        - Use plugins like the Performance Plugin or HTML Publisher Plugin to display JMeter reports directly in Jenkins.
    
    4. Automate Test Execution: Configure the pipeline to trigger performance tests automatically on specific events, such as every code commit, nightly builds, or after deployment to a staging environment.

## Summary

- In this chapter, you learned how to run JMeter tests in CLI mode and how to integrate JMeter with Jenkins or other CI/CD tools to automate performance testing as part of your software delivery pipeline. 

- This helps ensure continuous performance testing throughout the development lifecycle.

<div style="display: flex; justify-content: space-between; width: 100%; margin-top: 100px;">
    <a href="../Chapter-10/README.md" style="padding: 10px 20px; background-color: #007bff; color: white; text-decoration: none; border-radius: 5px;">Previous</a>
</div>