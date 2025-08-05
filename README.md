## Terraform and CPAR Variables Updater Script:

This Python script interactively updates Terraform variable files and related YAML configurations for Amazon EKS and Linode LKE clusters.

Supports creating both Amazon (EKS) and Linode (LKE) Clusters.

Prompts for necessary inputs with validation

This Script Updates the below files:

terraform.tfvars files (for LKE) or eks-terraform.tfvars (for EKS)

cpar-values.yaml

cpar-secrets.yaml


Certificate values must be updated manually; script provides clear reminders


Usage
Run the script from the build_env directory:

## 📂Current Directory Structure

<pre> 
eaa-lke-cpar/ 
 ├── build_env/ # Run the script from here │
      └── variable-updater.py 
 └── cpar-vars/ 
       ├── terraform.tfvars 
       ├── eks-terraform.tfvars 
       ├── cpar-values.yaml 
       └── cpar-secrets.yaml  </pre>

## Steps to run the Script

Make sure you have all the inputs and your desired configuration for Cluster and LoxiLB instances ready.

Enter the below command from build_env folder:

```python variable-updater.py```
Select cloud provider (Amazon or Linode).

Enter all requested inputs.

Preview changes and confirm to apply.

After Previewing changes and confirming everything is fine, provision infrastructure using Terraform Commands.


📝 Notes

Certificates (Filebeat ClientKey, VictoriaMetrics Key) are not updated automatically through this python script for now. Update them manually in cpar-secrets.yaml before or after running this script.
