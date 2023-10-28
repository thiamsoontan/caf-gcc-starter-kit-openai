# caf-gcc-starter-kit-openai


## Login to azure
```bash
az login --tenant [tenant id] 
az account set --subscription [subscription id]
```

## generate caf tfvars files
```bash
rover ignite --playbook "/tf/caf/ansible/gcc-starter-playbook.yml"
sudo chmod -R -f 777 /tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}
cd /tf/caf
```

## create gcc simulation environment
execute the steps in readme file: 
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/gcc_dev_env/README.md

## create launchpad
execute the steps in readme file: 
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/level0/launchpad/README.md

## create level3 networking
execute the steps in readme file: 
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/level3

## create level3 solution accelerators
execute the steps in readme file: 
/tf/caf/gcc_starter_{{prefix}}_{{caf_environment}}/landingzone/configuration/level4