# setup-protoc-action

This action makes the `protoc` compiler available to Workflows.

## Usage

To get the latest stable version of `protoc` just add this step:

```yaml
- name: Install Protoc
  uses: 4w3official/setup-protoc-action@v1
```

If you want to pin a major or minor version you can use the `.x` wildcard:

```yaml
- name: Install Protoc
  uses: 4w3official/setup-protoc-action@v1
  with:
    version: '22.3'
```

You can also require to include releases marked as `pre-release` in Github using the `include-pre-releases` flag (the dafault value for this flag is `false`)

```yaml
- name: Install Protoc
  uses: 4w3official/setup-protoc-action@v1
  with:
    version: '22.3'
    include-pre-releases: true
```

The action queries the GitHub API to fetch releases data, to avoid rate limiting,
pass the default token with the `repo-token` variable:

```yaml
- name: Install Protoc
  uses: 4w3official/setup-protoc-action@v1
  with:
    repo-token: ${{ secrets.GITHUB_TOKEN }}
```
