# ref
Produces a single output: the ref slug for GitHub actions

## Inputs
`nil`

## Outputs
### `slug`
If triggered from a branch workflow, this is the `${BRANCH}` from `refs/head/${BRANCH}`.

If triggered from a tag workflow, this is the `${TAG}` from `refs/tags/${BRANCH}`. 

## Example Usage
```yaml
steps:
- name: 'Get ref slug'
  id: ref
  uses: marcusljx-actions/ref@v1
  
- name: 'Use ref slug'
  run: |
    echo ${{ steps.ref.outputs.slug }}
```