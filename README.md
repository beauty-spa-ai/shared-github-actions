# shared-github-actions

## Usage

### Deploy K8S by argocd

```yaml
deploy:
  steps:
    - name: deploy k8s by argocd
      uses: sota-labs/shared-github-actions/deploy-k8s-by-argocd@v1
      with:
        image_name: sotalab-harbor.sotatek.works/topspotai/topspotai-chat-be
        image_tag: ${{ github.sha }}
        env: dev
        app_name: topspotai-chat-be
        argocd_project: topspot
        gitops_org: sota-labs
        gitops_repo: TopSpotAI-Infra-BaseImages
        gitops_path: gitops/topspotai-chat-be/overlays/dev
        argocd_host: ${{ vars.ARGOCD_HOST }}
        argocd_token: ${{ secrets.ARGOCD_TOKEN }}
        ssh_private_key: ${{ secrets.SSH_PRIVATE_TOKEN }}
```
