# VMware Tanzu RabbitMQ for VMs docs

This repo contains the VMware Tanzu RabbitMQ for VMs documentation.

In this README: 

- [Branches in this Content Repo](#branches-in-this-content-repo)
- [Releasing a New Minor Version](#releasing-a-new-minor-version)
- [Partials](#partials)
- [Contributing to Documentation](#contributing-to-documentation)
- [Publishing Docs](#publishing-docs)
- [Troubleshooting Markdown](#troubleshooting-markdown)
- [Style Guide](#style-guide)

## Branches in this Content Repo

The master branch is the tree-trunk, so ALWAYS make changes you want carried forward in this branch. This includes:

* Unreleased features
* Doc bug fixes
* Doc reorganization or enhancement

Then, if necessary, immediately cherry-pick/copy any changes that you want to push immediately to production into the appropriate branches listed below:

| Branch Name| Use for… |
|------------| ---------|
| master     | "edge" branch for v2.x, staged here: http://docs-pcf-staging.cfapps.io/rabbitmq-cf/2-n/index.html |
| 2.0        | v2.0 (http://docs.pivotal.io/rabbitmq-cf/2-0/)   |
| 1.21       | v1.21 (http://docs.pivotal.io/rabbitmq-cf/1-21/) |
| 1.20       | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-20/) |
| 1.19       | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-19/) |
| 1.18       | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-18/) |
| 1.17       | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-17/) |
| 1.16       | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-16/) |
| 1.15-live  | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-15/) |
| 1.14-live  | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-14/)|
| 1.13-live  | NOT IN USE docs have been deprecated (http://docs.pivotal.io/rabbitmq-cf/1-13/)|
| 1.12-live  | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.12.pdf)|
| 1.11-live  | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.11.pdf)|
| 1.10-live  | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.10.pdf)|
| 1.9-live   | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.9.pdf)|
| 1.8-live   | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.8.pdf)|
| 1.7-live   | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.7.pdf)|
| 1.6-live   | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.6.pdf)|
| 1.5-live   | NOT IN USE (PDF is here: https://docs.pivotal.io/archives/rabbitmq-pcf-1.5.pdf)|


## Releasing a New Minor Version

Because **master** is the latest and greatest documentation, the process would be to cut a **x.x** branch
for the version that **master** was targeting during that time.

After this point, **master** will then be the target for the next version of this product.


## Partials

Cross-product partials for these docs are single sourced from the [Docs Partials](https://github.com/pivotal-cf/docs-partials) repository.


## Contributing to Documentation

If there is some documentation to add for an unreleased patch version of these docs, then create a branch off of the **live** branch
you intend to modify and create a pull request against that branch.
After the version that change is targeting is released, the pull request can be merged and will be live
the next time a documentation deployment occurs.

If the documentation is meant to be target several released versions,
then you will need to:
+ create a pull request for each individual minor version
+ or ask the technical writer to cherry-pick to particular branches/versions.

For instructions on how to create a pull request on a branch and instructions on how to create a
pull request using a fork, see
[Creating a PR](https://docs-wiki.sc2-04-pcf1-apps.oc.vmware.com/wiki/external/create-pr.html)
in the documentation team wiki.


## Publishing Docs

- [docworks](https://docworks.vmware.com/) is the main tool for managing docs used by writers.
- [docsdash](https://docsdash.vmware.com/) is a deployment UI which manages the promotion from
staging to pre-prod to production. The process below describes how to upload our docs to staging,
replacing the publication with the same version.

### Prepare Markdown Files

- Markdown files live in this repo.
- Images should live in an `images` directory at the same level and linked with a relative link.
- Each page requires an entry in [config/toc.md](config/toc.md) for the table of contents.
- Variables live in [config/template_variables.yml](config/template_variables.yml).

### In Docsdash

1. Wait about 1 minute for processing to complete after uploading.
2. Go to https://docsdash.vmware.com/deployment-stage

   There should be an entry with a blue link which says `Documentation` and points to staging.

### Promoting to Pre-Prod and Prod

**Prerequisite** Needs additional privileges - reach out to a manager on the docs team [#tanzu-docs](https://vmware.slack.com/archives/C055V2M0H) or ask a writer to do this step for you.

1. Go to Staging publications in docsdash  
  https://docsdash.vmware.com/deployment-stage

2. Select a publication (make sure it's the latest version)

3. Click "Deploy selected to Pre-Prod" and wait for the pop to turn green (refresh if necessary after about 10s)

4. Go to Pre-Prod list  
  https://docsdash.vmware.com/deployment-pre-prod

5. Select a publication

6. Click "Sign off for Release"

7. Wait for your username to show up in the "Signed off by" column

8. Select the publication again

9. Click "Deploy selected to Prod"


## Troubleshooting Markdown

| Problem | List displays as a paragraph |
|---------|-----------|
| Symptom:| Bulleted or numbered lists look fine on GitHub but display as a single paragraph in HTML.|
| Solution: | Add a blank line after the stem sentence and before the first item in the list.|

| Problem | List numbering is broken: every item is `1.` |
|---------|-----------|
| Symptom:| Each numbered item in a list is a `1.` instead of `1.`, `2.`, `3.`, etc|
| Solution: | Try removing any blank newlines within each step.|

| Problem | Code boxes not showing |
|---------|-----------|
| Symptom:| VMware publishing system doesn't accept code tags after the three back ticks.|
| Solution: | Make sure you're not using `shell` or `bash` or `console` or `yaml` after back ticks.|


## Style Guide

Use this section to specify spelling of special words for VMware Tanzu RabbitMQ for VMs:

+ on-demand plan
+ shared-VM plan
+ dedicated-VM plan
+ RabbitMQ Management UI
