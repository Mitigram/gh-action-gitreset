# gh-action-gitreset

This GitHub [action] will `--hard` [reset] a branch to the content of another
branch and `--force` [push] it to the origin. By default, the source branch will
be the default branch at GitHub, and the destination branch will be the branch
where this action is run from, both according to the [context]. Note that
orphane workflows, e.g. when run from a [`schedule`][schedule] are anchored to
the default branch.

This action supposes that you have already a local copy of the repository, i.e.
that you already have run [`actions/checkout@v2`][checkout] at a prior step.

## Inputs

For the complete list of `inputs`, you can consult the file
[`action.yml`](./action.yml). Of particular interest is the input field called
`dry-run`: setting it to the string `"true"` will exercise the action, but not
push its result to the origin, thus keeping all your changes local to the
workflow.

  [action]: https://docs.github.com/en/actions
  [reset]: https://git-scm.com/docs/git-reset
  [push]: https://git-scm.com/docs/git-push#Documentation/git-push.txt---force
  [context]: https://docs.github.com/en/actions/learn-github-actions/contexts#github-context
  [schedule]: https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions#onschedule
  [checkout]: https://github.com/actions/checkout
