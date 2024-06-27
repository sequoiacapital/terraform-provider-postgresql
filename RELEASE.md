To release a new version, merge in the upstream, then push the version tag, suffixed with `-seq`.
A GitHub Actions workflow should take care of the rest.

Then go add this version to the `tf-init` script in the monorepo.

```
$ git remote add upstream git@github.com:cyrilgdn/terraform-provider-postgresql.git
$ git fetch --all
$ git merge --no-ff upstream/main  # resolve conflicts, favoring our previous changes
$ git push origin HEAD
$ git tag v1.20.0-seq
$ git push origin v1.20.0-seq
```
