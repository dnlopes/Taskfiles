# Taskfiles
This repository defines a set of [Taskfiles](https://github.com/go-task/task) for a wide range of use cases. These taskfiles provide agnostic primitives that serve as building blocks to orchestrate higher-level automations.

Below you can find a quick summary of each Taskfile:
* ```CICD```: primitives for CICD workflows (e.g., run pre-commit hooks)
* ```Terraform```: primitives for the whole lifecycle of a Terraform configuration. Required inputs:
  * **TF_CONFIG_DIR**: the path where the Terraform configuration is located
  * **TF_WORKSPACE**: the name of the Terraform workspace to use
  * **TFLINT_CONFIG_FILE**: the path for the tflint configuration file to use during linting
    * set ```SKIP_TFLINT=true``` if you want to skip this validation
  * **TF_INPUTS_FILE** (optional): the path for a ```tfvars``` files to use during plan and apply operations.
* ```GPG```: primitives to interact with GPG
  * **SOURCE_FILE**: the path of the source file to encrypt/decrypt
  * **DEST_FILE**: the path of the destination file to encrypt/decrypt
  * **KEY_ID**: the GPG key identifier to fetch/trust
  * **GPG_PUBLIC_KEY_SERVER** (optional): the GPG key server from where to fetch the GPG keys
    * default: keys.openpgp.org
* ```Homebrew```: a set of primitives to automate formulas and casks installs/upgrades
  * **FORMULA_NAME**: the name of the formula to install/update
  * **CASK_NAME**: the name of the formula to install/update
* ```AWS```: provides a wrapper to some AWS CLI actions
  * **FILE_PATH**: the file to download/upload
  * **S3_BUCKET_NAME**: the bucket name
  * **S3_OBJECT_KEY**: the bucket object to download/upload
