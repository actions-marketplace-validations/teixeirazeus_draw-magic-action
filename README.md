# draw-action

Draw Yu-Gi-Oh! Card on GitHub issue.

## Inputs

### `github-token`

**Required** The GitHub token used to create an authenticated client.

## Example usage

```yaml
name: Draw Yu-Gi-Oh! Card
on:
  issue_comment:
    types: [created, edited]

jobs:
  draw:
    runs-on: ubuntu-latest
    steps:
      - name: Draw Yu-Gi-Oh! Card on GitHub issue
        uses: Doarakko/draw-action@main
        if: >-
          contains(github.event.comment.body, 'draw')
          || contains(github.event.comment.body, 'ドロー')
        with:
          github-token: ${{secrets.GITHUB_TOKEN}}
```

## Demo

Please comment "draw" to [this issue](https://github.com/Doarakko/draw-action/issues/1)!