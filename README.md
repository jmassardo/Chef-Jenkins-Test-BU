# Chef-Jenkins-Test-BU

This repository is a sample of a BU's dedicated repository. This repo allows a BU to manage their own environment file and data bags and move at their own velocity.

## Data Bags

The `data_bags` folder contains standard data bag json files.

Example data bag folder structure:
```
data_bags
├── admin_users
│   ├── admin1.json
│   ├── admin2.json
│   └── admin3.json
├── limited_users
│   ├── user1.json
│   ├── user2.json
│   └── user3.json
└── op_users
    ├── op1.json
    ├── op2.json
    └── op3.json
```

## Environments

Put one or more json files in the `environments` folder. When the pipeline runs, they will be merged with the matching environment file from the `GlobalEnvironments` repo.

Sample Environment file:
``` json
{
  "name": "prod",
  "description": "Main env for prod servers",
  "cookbook_versions": {
    "security_audit": "~> 0.1.4",
    "base_config": "= 0.1.0"
  },
  "json_class": "Chef::Environment",
  "chef_type": "environment",
  "default_attributes": {
  },
  "override_attributes": {
  }
}
```