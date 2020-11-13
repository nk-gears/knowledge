# Iac

## Terraform

### Default files

### 1. terraform.tfvars

Hold Plain Variable with Values

```text
instance_name="test App"
instance_size=20
```

### 2. variables.tf

### Using Conditional Operators Inside Terraform

```text
environment_variables = {
"INSTANCE" = var.num_read_replicas == 0 ? format("%s",google_sql_database_instance.sql_instance.name ) : google_sql_database_instance.read_replica[0].name
}
```

## Azure Resource Manager

## Google Deployment Manager

## AWS Cloud Formation & CDK

