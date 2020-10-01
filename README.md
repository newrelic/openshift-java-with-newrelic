[![Community Project header](https://github.com/newrelic/open-source-office/raw/master/examples/categories/images/Community_Project.png)](https://github.com/newrelic/open-source-office/blob/master/examples/categories/index.md#community-project)

# NewRelic and Wildfly Docker Container

>[Brief description - what is the project and value does it provide? How often should users expect to get releases? How is versioning set up? Where does this project want to go?]

## Installation

**NOTE - this Docker container requires two things:**

1. An ISV / partner account with Red Hat as you need to run the container on a RHEL7 host
2. An account / license key from Newrelic - https://newrelic.com/signup

After getting the above, then proceed with the below

1. Install a RHEL7 host
2. Install Docker on that host
3. Download/clone this git repo
4. Build the container - `docker build -t wildfly/rhel7_newrelic .`
5. Once the container is built, you will need to run it and pass in some parameters:

`docker run -d -p 8080:8080 -p 9990:9990 -e JAVA_OPTS="-javaagent:/opt/jboss/wildfly/newrelic/newrelic.jar -Dnewrelic.config.license_key=xxxxxxxxxxxx -Dnewrelic.config.app_name=Java Agent Test on Wildfly" wildfly/test-app /opt/jboss/wildfly/bin/standalone.sh -b 0.0.0.0 -bmanagement 0.0.0.0`

6. The parameter -Dnewrelic.config.license_key=xxxxxxxxxxxx - this will be the license key string that you get from Newrelic account.
7. The parameter  -Dnewrelic.config.app_name=Java Agent Test on Wildfly - This will be the application name that will show up in the Newrelic UI. More details at Newrelic's Java Agent configuration file at ->
https://docs.newrelic.com/docs/agents/java-agent/configuration/java-agent-configuration-config-file
8. The port mappings (-p 8080 and 9990) will allow you to vefiy that Wildfly is running in your container - just go to http://localhost:8080 and you will see the interface. If you see the interface, then it is up and running properly
9. Once you verify that Wildfly is up and running, proceed to your account page on Newrelic and view your application monitoring page

For assistance on either one of the applications, please refer to http://wildfly.org/ and/or https://newrelic.com/support

## Getting Started
>[Simple steps to start working with the software similar to a "Hello World"]

## Support

Should you need assistance with New Relic products, you are in good hands with several support channels.

If the issue has been confirmed as a bug or is a feature request, file a GitHub issue.

**Support Channels**

* [New Relic Community](https://discuss.newrelic.com/tags/javaagent): The best place to engage in troubleshooting questions
* [New Relic Developer](https://developer.newrelic.com/): Resources for building a custom observability applications
* [New Relic University](https://learn.newrelic.com/): A range of online training for New Relic users of every level

## Privacy
At New Relic we take your privacy and the security of your information seriously, and are committed to protecting your information. We must emphasize the importance of not sharing personal data in public forums, and ask all users to scrub logs and diagnostic information for sensitive information, whether personal, proprietary, or otherwise.

We define “Personal Data” as any information relating to an identified or identifiable individual, including, for example, your name, phone number, post code or zip code, Device ID, IP address, and email address.

For more information, review [New Relic’s General Data Privacy Notice](https://newrelic.com/termsandconditions/privacy).

## Contribute

We encourage your contributions to improve [project name]! Keep in mind that when you submit your pull request, you'll need to sign the CLA via the click-through using CLA-Assistant. You only have to sign the CLA one time per project.

If you have any questions, or to execute our corporate CLA (which is required if your contribution is on behalf of a company), drop us an email at opensource@newrelic.com.

**A note about vulnerabilities**

As noted in our [security policy](../../security/policy), New Relic is committed to the privacy and security of our customers and their data. We believe that providing coordinated disclosure by security researchers and engaging with the security community are important means to achieve our security goals.

If you believe you have found a security vulnerability in this project or any of New Relic's products or websites, we welcome and greatly appreciate you reporting it to New Relic through [HackerOne](https://hackerone.com/newrelic).

If you would like to contribute to this project, review [these guidelines](./CONTRIBUTING.md).

To [all contributors](https://github.com/newrelic/openshift-java-with-newrelic/graphs/contributors), we thank you!  Without your contribution, this project would not be what it is today.

## License
`openshift-java-with-newrelic` is licensed under the [MIT](https://mit-license.org/) License.
