# copier-templates

This project is leveraging the project [Copier](https://copier.readthedocs.io/en/stable/) to allow us to not repeat ourselves and save time.


## How to use it

First you need to have copier installed, to do that simply run:

```bash
pip install copier
```

You should now have the command `copier` available in your terminal.

### Example of semantic release setup

In this project we have a template to enable the `semantic-release` on a Github project. 

Imagine you have the following folder structure:

```
.
└── my-awesome-project
    └── README.md
```

`my-awesome-project` is your github repository. Now you need to git clone `copier-templates` next to `my-awesome-project` to have the following structure:

```
.
├── copier-templates
└── my-awesome-project
    └── README.md
```

Good, now you can setup semantic-release, let's do it. 

Make sure you are in the your `my-awesome-project` and run:

```bash
copier ../copier-templates/github/semantic-release .
```

```
🎤 What is your project name?
   my-awesome-project
🎤 What version should we start from?
   0.0.1

Copying from template version None
 identical  .
    create  .github
    create  .github/package-lock.json
    create  .github/workflows
    create  .github/workflows/release.yml
    create  .github/package.json
    create  .github/.releaserc
```

Now your folder structure should look like this:

```
.
├── .github
│   ├── .releaserc
│   ├── package-lock.json
│   ├── package.json
│   └── workflows
│       └── release.yml
└── README.md
```

You should now be able to `git add ...`, `git commit ...`, `git push` and see the action running in Github.