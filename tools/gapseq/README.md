# gitlab_ci_galaxy_tools

This repository houses a template for Galaxy tools.

## Usage 
When creating a new project in the 'tools' group on GitLab, you can import this repository as a template.

This is done by following these steps:

1. Browse to the tools group (https://gitlab.com/LCAB-Bioinformatics/galaxy/tools)
2. Click 'New project' 
3. Select 'Create from template'
4. Go to the 'Group' tab
5. Click on this template

## Tool development
If you want to develop Galaxy tools, I recommend using the Visual Studio Code or an IDE derived from it. You can use the [galaxy-tools add-on](https://marketplace.visualstudio.com/items?itemName=davelopez.galaxy-tools) which will help your tool development by providing documentation, syntax highlighting, auto-closing of tags, linting and more.

If you need more details on the available options of a specific tag, you can reference the [Galaxy Tool XML File documentation](https://docs.galaxyproject.org/en/latest/dev/schema.html).


## CI/CD
This template includes a CI/CD pipeline that will automatically push the tool to the LCAB Galaxy Tool Shed (http://145.97.18.154/)
The pipeline has the following stages:
1. Tool lint stage: the tool xml is examined by the `planemo lint` command. This stage will fail if any errors are found (but warnings are OK)
2. Shed lint stage: the .shed.yml file is examined by the `planemo shed_lint` command. This stage will fail if any errors or warnings are found.
3. Deploy stage: the tool will be deployed on the LCAB Galaxy Tool Shed.

## Contact
If you experience any difficulties with this template, or if you have suggestions about how to improve it, you can open an issue on this template in GitLab or contact 