# LaboConnect 

[LaboConnect](https://laboconnect.com/) is a medical application. This template is in developement phase
It has to be used by non-docker/kubernetes users ! Team did his best to limit interaction with console...

## Before doing anything
In order to deploy an application, you'll have to pull containers images from a [private registry] (https://docker-01.progi.loc:5000/). This means that you need credentials. So the point is to verify that you have the good secret on your machine. First access the USERS Settings and pick the user specs. Then type the following command :

``` console
$ kubectl get secret --all-namespaces
```

## Explanations

The actual deployment launch 3 modules which are:
>  **HTTPD**: The frontal web.
> **Postgres**: The Data Base.
> **jBoss**: The LaboConnect application itself.

You'll have to choose the access port of you frontal web. The app will be accessed by the following url : `https://<hostname|ip>:<port>`
