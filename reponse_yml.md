# TP

## reponse commits conventional

```yaml
name: conventional commits 
on: 
  push:
    branches:
     - feature/**
     - hotfix/**



jobs:
  build:
    name: Conventional Commits
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - uses: webiny/action-conventional-commits@v1.0.5

  


 
##  reponse: les PR est ouverte depuis une branche feature/ ** vers la branche develop.

 ```yml

  name: feature/** vers la branch dev 

 on: 
   pull_request:
     branches:
       - dev

 jobs:
   build:
     if: startsWith(${{github.head.ref}}, "feature/")
     name: Conventional Commits
     runs-on: ubuntu-latest
     strategy:
       fail-fast: true
       matrix: 
         version: [14, 16]
       runs-on: ubuntu-latest
     steps:
       - uses: actions/setup-node@v3
         with: 
           node-version: ${{matrix.version}}

   ##  reponse: artifact pour stocker

```yml
name: Upload Artifact

on: workflow_dispatch

jobs:
  upload:
    name: upload
    runs-on: ubuntu-latest
    steps:
      - name: stocker les fichers
      
        run: "coucou toi artifact"
      - name: Upload Artifact
        uses: actions/upload-artifact@v3
        with:
          name: ci
          path: ci.txt

## reponse: branche issue

```yml
name: branche issue
on: 
  issues:
    types:
      - opened
env: 
  NAME:  c'est issues 

jobs:
  

    runs-on: ubuntu-latest
    steps:
      - name:
        if: ${issue.title}'
      