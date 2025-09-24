# 38200

Reproduction for [Renovate issue 38200](https://github.com/renovatebot/renovate/issues/38200).

## Current behavior

I am overwriting my **branchTopic** with the following **packagesRule**

```json
{
  "packageRules": [
    {
      "description": [
        "Disable automerge for patch and minor Typo3 updates"
      ],
      "matchManagers": [
        "composer"
      ],
      "matchPackageNames": [
        "typo3/**"
      ],
      "groupName": "Typo3 Packages Update",
      "branchPrefix": "renovate/{{{baseBranch}}}-",
      "branchTopic": "typo3-packages-update-grouped",
      "automerge": false
    }
  ]
}
```

however Renovate creates PR with branch _renovate/main-typo3-packages-update_ instead of _renovate/main-typo3-packages-update_**-grouped**

[https://github.com/uluzox/branchTopic/pull/3](https://github.com/uluzox/branchTopic/pull/3)

## Expected behavior

### Commit hash pinning disabled

PR is created with branch name _renovate/main-typo3-packages-update_**-grouped**
