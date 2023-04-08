# helm-basic
repo to understand basics of helm

## install helm

ref : https://helm.sh/docs/intro/install/


## What are Helm and Helm chart?

Helm is a package manager for Kubernetes and helps to manage Kubernetes applications. And helm chart repository is an HTTP server that houses an index.yaml file and optionally some packaged charts.

### Create helm repo using github pages

#### Github Pages?
We can create a chart repository using GitHub Pages. It allows us to serve static web pages. All we need is to host a single index.yaml file along with a bunch of .tgz files.


- Let's start by creating a new git repo in the Github account.
- Clone the empty repo


##### enable github pages

Go to the settings page on your repository, then look for pages, make sure the site is published

#### Create a chart and upload to the repository

```

# create a chart

helm create <chart name>

# package the chart

helm package ./<chart name>

```

***example*** 

```
user@Air helm % helm create wordpress
Creating wordpress
user@Air helm % ls -ltr
total 0
drwxr-xr-x  7 user  staff  224 May 18 13:20 wordpress
user@Air helm % helm package ./wordpress 
Successfully packaged chart and saved it to: /Users/sceva/Documents/lwplabs/kubernetes/helm/wordpress-0.1.0.tgz
user@Air helm % ls -ltr
user@Air helm % ls -ltr
total 8
drwxr-xr-x  7 user  staff   224 May 18 13:20 wordpress
-rw-r--r--  1 user  staff  3762 May 18 13:20 wordpress-0.1.0.tgz

```

#### Copy the chart (tgz) file to the Git repo

```
cp wordpress-0.1.0.tgz <local git code>
```

#### Generate or update the index.yaml

```
helm repo index .

```
#### push the code to github

#### Add repo to your workstation or laptop

```

helm repo add <github pages url>

```

#### list the repo 

```

helm repo list

```




