# alfasoft-mario
Exercício Infrastructure + Devops

Code Quality Check


Develop a process to automatically check code quality
Features

The process should do the following:

1 - Run a self contained process within a docker container

2 - Pull latest commit from a given repository and run tool on it

3 - Extract results into a folder for submission

Tools to use

There are a lot of code quality tools in the market, for different programming languages.

The goal is to build a system for PHP which includes static code analysis, code refactoring suggestions and PSR validations, amongst others.

A list of multiple tools will be left below. The number of tools configured will be one of the evaluation scoring factors.

Tools in order of importance (links are in the end of the exercise): Sonarqube, PHPMD, PHPMetrics, CodeInsight, AWap, Exacat, ProgPilot, PHPCPD
Process
Each of the tools should run on its own docker container.

Each tool should run separately, so multiple tools can be used and processes can be reordered.

If the 3 steps mentioned in the features can be ran in a single container, a dockerfile should be used. If containers for the tool exist, but they do not include git features, a different container can be used for providing git features, and a docker-compose file should be used for the task.
Detailed Instructions
There should be a container or multiple containers responsible for running each tool. If a web server is needed to run the tool, there can be a container for nginx or apache, another for composer and / or php if needed.

A multi-purpose container can also be configured for each of the tasks, but the ability to reuse containers across multiple tools will be considered a bonus point.

At the end of the execution, some tools will output the result to the console, while others will generate files and / or folders of reports. If the output is written to the console, it should also be written to a file in a specific location. If the output is one or multiple files, they should also be written to a specific location.

Each tool and container (or set of containers) should have parameters sent to it, which determine:

1 - The URL of the repository being tested
2 - The folder where the output should be written to

Example:
docker run sonarqube https://github.com/symfony/symfony.git /var/reports/sonarqube/20210215

Development steps

1 - Do the development of the features locally on your machine.

2 - Push new versions of each tool’s docker configuration to a git repository for assessment.

NOTE: Do frequent pushes as modifications are made to the scripts, so progress can be assessed.



Links do Tools

https://www.sonarqube.org/downloads/

https://phpmd.org/download/index.html

https://github.com/phpmetrics/PhpMetrics

https://github.com/console-helpers/code-insight

http://awap.sourceforge.net/support.html

https://www.exakat.io/en/exakat-community-edition/

https://github.com/designsecurity/progpilot

https://github.com/sebastianbergmann/phpcpd


