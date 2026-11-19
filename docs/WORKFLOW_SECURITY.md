# Workflow security

Pin external actions in write-enabled workflows to a full commit SHA from
the action's upstream repository. Keep the release tag in a comment so
maintainers can review and update the pin. For an upstream action that
uses a moving branch, review the commit before updating the pin.

The site build has read-only access, including on pull requests. Only a
build from the default branch can pass an artifact to the deployment job.
That job has write access to update the Pages publishing branch.

[GitHub Actions secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)
