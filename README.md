# terraform-validate-action

Suggested use:

```yaml
  plan:
    name: Terraform Plan (dev)
    environment:
      name: dev-plan
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: ${{ env.tf_actions_working_dir }}
    steps:
      - name: Terraform Validate
        uses: vivantehealth/terraform-validate-action@main
      - name: Terraform Plan
        uses: vivantehealth/terraform-plan-action@main
        with:
          gcp_key: ${{ secrets.GCP_KEY }}
          domain_project_id: ${{ secrets.DOMAIN_PROJECT_ID }}
          terraform_project_id: ${{ secrets.TERRAFORM_PROJECT_ID }}
          secrets_provisioning_private_key: ${{ secrets.SECRETS_PROVISIONING_PRIVATE_KEY }}
```
