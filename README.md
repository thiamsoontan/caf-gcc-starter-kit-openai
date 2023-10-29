# caf-gcc-starter-kit-openai


## Login to azure
```bash
az login --tenant [tenant id] 
az account set --subscription [subscription id]
```

## configure gcc definition file
add your subscription id to the below file
```bash
/tf/caf/definition/config_gcc.yaml
```

## generate caf tfvars files
```bash
rover ignite --playbook "/tf/caf/ansible/gcc-starter-playbook.yml"
sudo chmod -R -f 777 /tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}
cd /tf/caf
```

## create GCC Development Environment
go to readme file: 
```bash
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/gcc_dev_env/README.md
```
execute the steps:
```bash
cd /tf/caf/gcc_starter_escep_uat/landingzone/configuration/gcc_dev_env

terraform init

terraform plan

terraform apply

cd /tf/caf/
```

## create launchpad
go to readme file: 
```bash
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/level0/launchpad/README.md
```
execute the steps:
```bash
rover -lz /tf/caf/landingzones/caf_launchpad \
  -launchpad \
  -var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level0/launchpad \
  -skip-permission-check \
  -env uat \
  -a plan
```

## create level3 networking
execute the steps in readme file: 
```bash
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/level3
```

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/shared_services/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_management/README.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_internet/README.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_devops/README.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_hub_internet/README.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/ingress_internet/firewall/README.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/ingress_internet/agw/Readme.md



## create level4 solution accelerators
execute the steps in readme file: 
```bash
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/level4
```

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/devops/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/management/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/acr/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/agw/Readme.md


/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/container_instance/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/cosmosdb/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/keyvault/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/linux_function_app/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/openai_service/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/search_service/Readme.md

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level4/project/storage_account/Readme.md

