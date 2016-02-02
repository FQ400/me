# Please rebase your commits

The request 'Please rebase your commits.' were often said by colleagues of mine.
Often heared but never understood.

Some facts why it is good to use rebase.

- clean history without merge commits (depends on style)
- when using github flow, PR (pull request) reviews are much more easier (depending on team size)
  - master have to be rebased all the time


Github Flow:

Shared feature development

The is a story which is devided into tasks.
2 weeks of master rebase into a feature branch which will contain multiple task branches.
The more commits in that feature branch the more commits have to be rebased when the master changes.
This takes time. A lot of time and the downside is the whole rebase has to be repeated in every task branch.
Maybe it goes fast but not valid.

If you not familiar with rebase, get familiar. The more you use it the better you get the less afraid you are on
hugh rebases of 100 commits.

Some 'tools' to make a rebase easier for yourself.

`git commit --fixup <commit_id>` && `git rebase -i --autosquash <commit_id>`
http://fle.github.io/git-tip-keep-your-branch-clean-with-fixup-and-autosquash.html
