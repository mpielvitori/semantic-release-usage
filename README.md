# Semantic release basic usage

Semantic release automates the whole package release workflow including: determining the next version number, generating the release notes and publishing the package.

This removes the immediate connection between human emotions and version numbers, strictly following the [Semantic Versioning](https://semver.org/) specification.

### Custom configuration
Everything is taken based on the sources mentioned at the [bottom of this page](#references) except the custom configuration to get the version before creating it in order to use when tagging images with the same version of the tag to be created.

In this project I just log the version to keep it simple `echo "Version -> $(cat version)"` you can use it for something else or skip the execution of sem-rel in `dry-run` in case you don't need it.

## GitLab usage

1. Push access to the remote repository
[semantic-release](https://github.com/semantic-release/semantic-release) requires push access to the project Git repository in order to create Git tags. The Git authentication can be set with one of the following environment variables:
`GL_TOKEN` or `GITLAB_TOKEN` [A GitLab personal access token](https://docs.gitlab.com/ce/user/profile/personal_access_tokens.html)
1. Run semantic-release only after all tests succeeded.
  * Configure [gitlab pipelines](https://docs.gitlab.com/ee/ci/pipelines/index.html) taking as an example the `.gitlab-ci.yml` file.
  * `@semantic-release/changelog` and `@semantic-release/git` plugins are required to record changes in a file [CHANGELOG.md](./CHANGELOG.md)
  * Configure semantic release taking as an example the `.releaserc.js` file.

## References
* [Semantic release Wiki](https://semantic-release.gitbook.io/semantic-release/)
* [Semantic release project](https://github.com/semantic-release/semantic-release)
