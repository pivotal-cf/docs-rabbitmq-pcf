# VMware RabbitMQ for Tanzu Application Service docs

This repo contains the VMware RabbitMQ for Tanzu Application Service documentation.

In this README:

- [VMware RabbitMQ for Tanzu Application Service docs](#vmware-rabbitmq-for-tanzu-application-service-docs)
  - [Branches](#branches)
  - [Releasing a new minor version](#releasing-a-new-minor-version)
  - [Partials](#partials)
  - [Contributing to documentation](#contributing-to-documentation)
  - [Publishing docs](#publishing-docs)
    - [Prepare Markdown files](#prepare-markdown-files)
    - [In Docsdash](#in-docsdash)
    - [Promoting to pre-prod and prod](#promoting-to-pre-prod-and-prod)
  - [Troubleshooting Markdown](#troubleshooting-markdown)
  - [Style guide](#style-guide)


## Branches

The master branch is the tree-trunk, so ALWAYS make changes you want carried forward in this branch. This includes:

* Unreleased features
* Doc bug fixes
* Doc reorganization or enhancement

Then, if necessary, immediately cherry-pick/copy any changes that you want to push immediately to production into the appropriate branches listed below:

| Branch Name | Staging | Prod  |
|-------------| ---------|------|
| main      | [v2.5](https://docs-staging.vmware.com/en/draft/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.5/tanzu-rmq/GUID-index.html) | N/A |
| 2.4  | [v2.4](https://docs-staging.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.4/tanzu-rmq/GUID-index.html)      | [v2.4](https://docs.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.4/tanzu-rmq/GUID-index.html)   |
| 2.3  | [v2.3](https://docs-staging.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.3/tanzu-rmq/GUID-index.html)      | [v2.3](https://docs.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.3/tanzu-rmq/GUID-index.html)   |
| 2.2  | [v2.2](https://docs-staging.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.2/tanzu-rmq/GUID-index.html)      | [v2.2](https://docs.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.2/tanzu-rmq/GUID-index.html)   |
| 2.1  | [v2.1](https://docs-staging.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.1/tanzu-rmq/GUID-index.html)      | [v2.1](https://docs.vmware.com/en/VMware-Tanzu-RabbitMQ-for-Tanzu-Application-Service/2.1/tanzu-rmq/GUID-index.html)   |
| 2.0        | NOT IN USE  |
| 1.21       | NOT IN USE |
| 1.20       | NOT IN USE |
| 1.19       | NOT IN USE |
| 1.18       | NOT IN USE |
| 1.17       | NOT IN USE |
| 1.16       | NOT IN USE |
| 1.15       | NOT IN USE |
| 1.14  | NOT IN USE |
| 1.13  | NOT IN USE |
| 1.12  | NOT IN USE |
| 1.11  | NOT IN USE |
| 1.10  | NOT IN USE |
| 1.9    | NOT IN USE |
| 1.8   | NOT IN USE |
| 1.7   | NOT IN USE |
| 1.6   | NOT IN USE |
| 1.5   | NOT IN USE |

## Releasing a new minor version

Because **master** is the latest and greatest documentation, the process would be to cut a **x.x** branch
for the version that **master** was targeting during that time.

After this point, **master** will then be the target for the next version of this product.


## Partials

Cross-product partials for these docs are single sourced from the [Docs Partials](https://github.com/pivotal-cf/docs-partials) repository.

## Contributing to documentation

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

## Publishing docs

- [docworks](https://docworks.vmware.com/) is the main tool for managing docs used by writers.
- [docsdash](https://docsdash.vmware.com/) is a deployment UI which manages the promotion from
staging to pre-prod to production. The process below describes how to upload our docs to staging,
replacing the publication with the same version.

### Prepare Markdown files

- Markdown files live in this repo.
- Images should live in an `images` directory at the same level and linked with a relative link.
- Each page requires an entry in [config/toc.md](config/toc.md) for the table of contents.
- Variables live in [config/template_variables.yml](config/template_variables.yml).

### In Docsdash

1. Wait about 1 minute for processing to complete after uploading.
2. Go to https://docsdash.vmware.com/deployment-stage

   There should be an entry with a blue link which says `Documentation` and points to staging.

### Promoting to pre-prod and prod

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

## Style guide

Use this section to specify spelling of special words for VMware RabbitMQ for Tanzu Application Service:

+ on-demand plan
+ shared-VM plan
+ dedicated-VM plan
+ RabbitMQ Management UI
