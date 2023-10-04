# nf_modules

**Central module resource for the LMS Nextflow pipelines.**

`nf_modules` stores a shared `nextflow.config` file and submodules for use across
pipelines, allowing updates to be rolled out from a central point.

To avoid the complexities of `git submodules` having to be cloned using `--recursive`,
`nf_modules` can be included as a `git subtree`:

```
# git clone git@github.com:LMSBioinformatics/nf_dummy.git
# cd nf_dummy

git remote add -f nf_modules git@github.com:LMSBioinformatics/nf_modules.git
git subtree add --prefix nf_modules nf_modules main --squash
```

Following changes to `nf_modules`, updates can be pulled to individual pipelines:

```
git fetch nf_modules main
git subtree pull --prefix nf_modules nf_modules main --squash
```
