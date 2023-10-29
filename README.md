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
```bash
rover -lz rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/shared_services \
-env uat \
-skip-permission-check \
-tfstate shared_services.tfstate \
-a plan
```

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_management/README.md
```bash
rover -lz rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_management \
-parallelism 30 \
-env uat \
-tfstate networking_spoke_management.tfstate \
-a plan
```

/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_internet/README.md
```bash
rover -lz rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_internet \
-env uat \
-tfstate networking_spoke_internet.tfstate \
-a plan
```


/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_devops/README.md
```bash
rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_spoke_devops \
-parallelism 30 \
-env uat \
-tfstate networking_spoke_devops.tfstate \
-a plan
```


/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_hub_internet/README.md
```bash
rover -lz rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/networking_hub_internet \
-env uat \
-tfstate networking_hub_internet.tfstate \
-a plan
```


/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/ingress_internet/firewall/README.md
```bash
rover -lz rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/ingress_internet/firewall \
-parallelism 30 \
-env uat \
-tfstate networking_firewall_ingress_internet.tfstate \
-a plan
```


/tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/ingress_internet/agw/Readme.md
```bash
rover -lz rover -lz /tf/caf/landingzones/caf_solution \
-level level3 \
-var-folder /tf/caf/gcc_starter_escep_uat/landingzone/configuration/level3/ingress_internet/agw \
-env uat \
-tfstate solution_accelerators_agw_internet_ssl.tfstate \
-a plan
```




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

