# Exercise 11.1 - Warming Up

Think about a hypothetical situation where we have an application being worked on by a team of about 6 people. The application is in active development and will be released soon. <br>

Let us assume that the application is coded with some other language than JavaScript/TypeScript, e.g. in Python, Java, or Ruby. You can freely pick the language. This might even be a language you do not know much yourself. <br>

Write a short text, say 200-300 words, where you answer or discuss some of the points below. You can check the length with https://wordcounter.net/. Save your answer to the file named exercise1.md in the root of the repository that you shall create in [exercise 11.2](https://fullstackopen.com/en/part11/getting_started_with_git_hub_actions#exercise-11-2). <br>

The points to discuss: <br>

- Some common steps in a CI setup include linting, testing, and building. What are the specific tools for taking care of these steps in the ecosystem of the language you picked? You can search for the answers by google.
- What alternatives are there to set up the CI besides Jenkins and GitHub Actions? Again, you can ask google!
- Would this setup be better in a self-hosted or a cloud-based environment? Why? What information would you need to make that decision?
  Remember that there are no 'right' answers to the above!

# Solution exercise 11.1

- Assuming that we are building a `Python` application. For linting, we can consider using either `Pylint` or `PyFlakes`. For unit and integration tests, we can use `pytest`. The code will be linted and tested using the aforementioned tools before being merged into the main branch or master. The branch won't be merged until all tests are successful. We can construct a docker container of the app and automatically deploy it using, for instance, GitHub Actions.

- Alternatives for setting up CI:
    - GitLab CI
    - Atlassian Bamboo
    - CircleCI
    - TeamCity
    - Travis CI
    - AWS CodePipeline
    - Azure Pipelines

 <br>

- Self-hosted: <br>
Jenkins is a popular self-hosted option due to its flexibility and plugins for various applications. It allows for complete control over the environment, resources, and hardware usage. However, it is complicated to set up, often requiring boilerplate and template code for builds. Additionally, CI/CD must be set up with Jenkins' domain-specific language, and there are risks of hardware failures if the setup is heavy. Self-hosted options typically have billing based on the hardware, with no changes to the server's billing.

- Cloud-based: <br>
Cloud-hosted setups do not require any setup of the environment, as they are already configured for you. To configure a cloud-based option, simply put a file in your repository and instruct the CI system to read or check for it. Cloud-based options may be simpler if you stay within normal usage, but they may become more limited or difficult to perform specific tasks. More complicated setups may require specific hardware resources, such as a GPU. Resource limitations on cloud-based platforms can affect performance, as self-hosted setups can use a larger server to increase resources, while cloud-based options may not. For instance, GitHub Actions has nodes with 2 vCPUs and 8GB of RAM. Additionally, cloud-based options are typically billed by build time, which is a factor to consider.

- Conclusion: <br>
Since we are working on a small to medium software project that doesn't have any special requirements (e.g. a need for a graphics card to run tests), a cloud-based solution is probably best. The configuration is simple and we don't need to go to the hassle or expense of setting up our own system. For smaller projects especially, this should be cheaper.