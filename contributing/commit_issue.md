# <a name="commit_issue"></a> Unreasonable Commit Issue Submitting

If you find a unreasonable commit in the history, you can help us by submit-issue. Or even better, you can [Submit a Pull Request](./pull_request.md) with a fix.

We next provide some guidelines for modifying the original commit.

## <a name="commit_fix"></a> Fixing a Unreasonable Commit

In multi-person collaboration scenarios, writing personal submissions is of great benefit to submission development efficiency and promoting teamwork. 

As developers, we should try to minimize the confusion about code changes caused by reading other people's or older code.

In a multi-person collaboration scenario, specifically, unreasonable submissions will have the following problems:

- Increase the difficulty of review by reviewers

- Commit lacks atomicity

- If a commit contains many functions, it is difficult to describe the commit information clearly.

Judging from the current enterprise-level projects in the industry, most commit messages follow one principle, that is, 'do one thing and do it well'. 

Only one complete small thing is done in a submission, but it is done well at one time. We The solution also adopts this principle for analysis and practice.

Here are a few examples of scenarios where the original unreasonable submissions are split:

### <a name="last"></a> Recent Unreasonable Commit

Scenario 1: Split the header submission, which involves three operations:

- Delete setup.py

- Added new file main.py

- Fix known bugs

Split the current C into three small submissions, and each new small submission completes one of the above three operations

The specific steps are: 
1. first roll back the master branch once, the last commit at this time is still retained in the workspace, and point the branch to the parent node of the latest commit. 

```shell
git reset -HEAD ~1
```

2. then separate the original changes involving the three parts through three different commits. Make a submission.

```shell
git add -p <Related documents>
git commit
```

### <a name="history"></a> History Unreasonable Commit

Scenario 2: Split historical submission B. The three operations involved in historical submission are the same as scenario 1 above.

The specific steps are: 

1. roll back the master branch to before commit B. 

At this time, git will open an editor and write the commits involved in the rebase into an action file. 

The editor will display pick B and pick in this scenario. C, change pick B to edit B and then save and exit. 

```shell
git rebase -i B^
```

2. At this time, B becomes the commit currently pointed to by the master branch. Then use the method of scenario 1 to split B into B1, B2, and B3, 

```shell
git reset -HEAD ~1
```

```shell
git add -p <Related documents>
git commit
```

3. finally use the continue option in git rebase. Resubmit commit C to B3 to generate a new commit C

```shell
git rebase --continue
```