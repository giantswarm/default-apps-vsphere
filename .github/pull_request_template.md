This PR:

- adds/changes/removes etc

### Checklist

- [ ] Update changelog in CHANGELOG.md.
- [ ] Make sure `values.yaml` and `values.schema.json` are valid.

### Testing

Description on how default-apps-vsphere can be tested.

- [ ] fresh install works
- [ ] upgrade from previous version works

### Trigger e2e tests

<!--
We currently have one pipeline that tests both cluster creation and cluster upgrades. You can trigger this pipeline by writing this commands in a pull request comment or description
- `/run cluster-test-suites`

If for some reason you want to skip the e2e tests, remove the following line.

Note: Tests are not automatically executed when creating a draft PR
If you do want to trigger the tests while still in draft then please add a comment with the trigger.
-->

/run cluster-test-suites
