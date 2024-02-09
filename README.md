# opendatahub-crds

This repository contains fluent classes for our oDH e2e test suite.
The main goal for making the classes available through the external repository is to speed up the build of [odh-e2e test suite](https://github.com/skodjob/odh-e2e).

The source CRDs are copied from [opendatahub-operator](https://github.com/opendatahub-io/opendatahub-operator) repository and are stored in our repository for [configuration files](https://github.com/skodjob/sokar/tree/main/open-data-hub/client).
All updates are done automatically every night if a new version of ODH operator is available. 
New versions of fluent classes are built, pushed to github storage and then a new version is set in test suite.

For more information how the generator works see the [documentation](https://github.com/fabric8io/kubernetes-client/blob/main/doc/java-generation-from-CRD.md).

## How to Generate and Publish io.odh.opendatahub-crds
_Note: this process is optional, you could re-use the package from the repo https://github.com/skodjob/opendatahub-crds to author new tests_

1. Fork this repo to your account
1. Edit the pom.xml
    - replace https://github.com/skodjob/opendatahub-crds with the url of your fork
    - replace https://maven.pkg.github.com/skodjob/opendatahub-crds with the maven pkg url of your fork (i.e., replace skodjob with your username)
    - (Optional) Edit the URLs under `<plugin>/<configuration>/<urls>` in order to use your selection of CRDs
1. Generate a Github token (classic) with `write:packages` permissions
1. Set `~/.m2/settings.xml` to use the token. More info at Github official doc [Authenticating with a personal access token](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry#authenticating-with-a-personal-access-token)
1. from your terminal, run `mvn deploy`
    - use `mvn deploy -X` for full stack error messages