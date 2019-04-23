# Why use virtual environments
> Keeping libraries straight with virtual environments

- Work on multiple Python projects
- Need a way easily to bundle projects with all associated libraries
- Be worried about potential conflicts between installed libraries

To solve each problem mentioned above, you may need install a Python virtual environment to keep everything separated and easy to manage.

# How to use virtualenv
When you install a Python library without a virtual environment, you're install it **globally**.
> It resembles `npm install -g pacakage`

Fortunately, with ***virtualenv*** we can install project-associated libraries **locally**. And creating a virtual environment is easy:
> It resembles `npm install -save pacakage`

```bash
$ virtualen exampleEnv
```
This creates a new environment called ***exampleEnv***, which you must **activate** in orer to use:

```bash
$ cd exampleEnv
$ source bin/activate
```
You can leave the environment with the **deactivate** command, after which you can no longer access any libraries that were installed inside the virtual environment.
```bash
$ deactivate
```
