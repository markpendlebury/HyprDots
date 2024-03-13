#!/bin/bash

# A Collection of functions to assist in working with Terraform
# Each function has two possible options, one utilises a basic
# terraform configuration and the other utilises specific
# environment variables

# Terraform init
tfi() {
        if [ -z "$1" ]; then
                rm -rf .terraform && rm -f .terraform.lock.hcl
                terraform init
        else
                rm -rf .terraform && rm -f .terraform.lock.hcl
                terraform init --var-file=environment/"$1"/variables.tfvars --backend-config=environment/"$1"/state.tfvars
        fi
}

# Terraform plan
tfp() {
        if [ -z "$1" ]; then
                terraform plan
        else
                terraform plan -var-file=environment/"$1"/variables.tfvars
        fi
}

# Terraform plan all environment:
tfp.all() {
        for d in environment/*; do
                ALIAS="${d#environment/}"
                figlet $ALIAS
                getcredentials ont-$ALIAS

                rm -rf .terraform .terraform.lock.hcl
                terraform init --backend-config=environment/$ALIAS/state.tfvars
                terraform plan --var-file=environment/$ALIAS/variables.tfvars
        done
}

# Terraform apply all environments:
tfa.all() {
        for d in environment/*; do
                clear
                ALIAS="${d#environment/}"
                figlet $ALIAS
                getcredentials ont-$ALIAS

                rm -rf .terraform .terraform.lock.hcl
                terraform init --backend-config=environment/$ALIAS/state.tfvars
                terraform apply --var-file=environment/$ALIAS/variables.tfvars

        done
}

# Terraform apply
tfa() {
        if [ -z "$1" ]; then
                terraform apply
        else
                terraform apply -var-file=environment/"$1"/variables.tfvars
        fi
}

# Terraform destroy
tfd() {
        if [ -z "$1" ]; then
                terraform destroy
        else
                terraform destroy -var-file=environment/"$1"/variables.tfvars
        fi
}

# This function utilises https://cost.modules.tf,
tfcost() {
        echo "Calulating cost estimate..."
        if [ -z "$1" ]; then
                terraform plan -out=plan.tfplan >/dev/null
        else
                terraform plan -var-file=environment/"$1"/variables.tfvars -out=plan.tfplan >/dev/null
        fi
        terraform show -json plan.tfplan | curl -s -X POST -H "Content-Type: application/json" -d @- https://cost.modules.tf | jq
}

# This function adds the ability to easily install and switch
# to specific versions of terraform

tfswitch() {
        export LOCAL_BIN=~/.tfswitch/bin

        if [ ! -d $LOCAL_BIN ]; then
                mkdir -p $LOCAL_BIN
        fi

        echo "Switching to Terraform version: $1..."

        TF_BINARY=$LOCAL_BIN/terraform_"$1"

        if [ ! -f "$TF_BINARY" ]; then
                wget -q -O $LOCAL_BIN/terraform_"$1".zip https://releases.hashicorp.com/terraform/"$1"/terraform_"$1"_linux_amd64.zip
                unzip -qq $LOCAL_BIN/terraform_"$1".zip -d $LOCAL_BIN
                mv $LOCAL_BIN/terraform $LOCAL_BIN/terraform_"$1"
                sudo chmod +x "$TF_BINARY"
                rm $LOCAL_BIN/terraform_"$1".zip
        fi

        unlink ~/.local/bin/terraform
        ln "$TF_BINARY" ~/.local/bin/terraform
        echo "Done!"
}
