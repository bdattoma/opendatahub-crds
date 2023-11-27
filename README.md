# opendatahub-crds

This repository contains fluent classes for our oDH e2e test suite.
The main goal for making the classes available through the external repository is to speed up the build of [odh-e2e test suite](https://github.com/skodjob/odh-e2e).

The source CRDs are copied from [opendatahub-operator](https://github.com/opendatahub-io/opendatahub-operator) repository and are stored in our repository for [configuration files](https://github.com/skodjob/sokar/tree/main/open-data-hub/client).
All updates are done automatically every night if a new version of ODH operator is available. 
New versions of fluent classes are built, pushed to github storage and then a new version is set in test suite.

For more information how the generator works see the [documentation](https://github.com/fabric8io/kubernetes-client/blob/main/doc/java-generation-from-CRD.md).
