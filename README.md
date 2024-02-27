# Sample JDL files for JHipster v8+

This repository is a showcase of JDL schema files.

Please add your own or create an issue if you'd like to see a particular one added.

Run `jhipster jdl myfile.jdl filename.jdl` just pass any file name from this repo and it will automatically be fetched.

It's possible to customize the generated project by passing options `jhipster jdl default.jdl --client-framework vue --build gradle`. Run `jhipster app --help` for more choices.

## Try Sample JDL in OpenShift Dev Spaces

### JHipster & PyHipster Generator Tekton Pipeline (Oficial JHipster v8.1.0 & PyHipster 0.0.9)

<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio-jhipster.PNG?raw=true" width="684" title="Run On Openshift">
</p>
<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio-pyhipster.PNG?raw=true" width="684" title="Run On Openshift">
</p>

### Install JHipster & PyHipster Generator on OpenShift Dev Spaces

1. Login with your Red Hat Account. https://console.redhat.com/openshift/sandbox. Select "OpenShift Dev Spaces".

<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/redhat-console.PNG?raw=true" width="684" title="Run On Openshift">
</p>

2. Fork this repo and complete Git Repo URL parameter with your repo info.

<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/install-jhipster-devspace.PNG?raw=true" width="684" title="Run On Openshift">
</p>


3. Open terminal on Red Hat OpenShift Dev Spaces and run oc apply command

```
oc apply -f jhipster-pyhipster-generator-tekton-pipeline.yaml 
```

```
Output
jdl-samples (v8) $ oc apply -f jhipster-pyhipster-generator-tekton-pipeline.yaml  
persistentvolumeclaim/workspace created
task.tekton.dev/cleanup-workspace created
task.tekton.dev/pyhipster-generator created
task.tekton.dev/jhipster-generator created
pipeline.tekton.dev/jhipster-pyhipster-generator-pipeline created
```

4. Generate Access Token from your gitlab repo with api, read_repository, write_repository rule.

```
https://gitlab.com/-/user_settings/personal_access_tokens 
```

<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio-gitlab-access-token.PNG?raw=true" width="684" title="Run On Openshift">
</p>


5. Run pipeline jhipster-pyhipster-generator-pipeline on OpenShift Pipeline. Complate de GITLAB paramaters with your repo info and JHipster o PyHipster generate.

<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio.PNG?raw=true" width="684" title="Run On Openshift">
</p>


<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio-form.PNG?raw=true" width="684" title="Run On Openshift">
</p>
<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio-push.PNG?raw=true" width="684" title="Run On Openshift">
</p>

6. Check your GitLab Repository to see if the app was created.
<p align="left">
  <img src="https://github.com/maximilianoPizarro/jhipster-devspace/blob/master/screenshot/jhipster-generator-dockerio-gitlab.PNG?raw=true" width="684" title="Run On Openshift">
</p>

NOTE: Custom tasks "cleanup-workspace" fail but work because remove all files from directory workspace and don't remove mountpath.


6. Open your new project autogerate in a new DevSpace workspace, build and run project in dev mode.
<p align="left">
  <img src="https://raw.githubusercontent.com/maximilianoPizarro/pyhipster-devspace/main/screenshot/pyhipster-terminal-run.PNG" width="684" title="Run On Openshift">
</p>