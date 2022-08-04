**This repository is an unofficial fork**

---

Terraform Provider
==================

Usage
-----

```hcl
terraform {
  required_providers {
    mysql = {
      source  = "grigoriy0/mysql"
      version = "1.9.6"
    }
  }
  required_version = ">= 0.13"
}

provider "mysql" {
  endpoint = "127.0.0.1"
  password = "my-super-password"
  username = "username"
}
```

Usage with AWS Secret
---

```hcl
terraform {
  required_providers = {
    mysql = {
      source  = "grigoriy0/mysql"
      version = "1.9.6"
    }
  }
  required_version = ">= 0.13"
}

provider "mysql" {
  endpoint = "rds-host"
  username = "rds-root"
  aws_secret = {
    secret_name = "rds-credentials-secret"
    region      = "us-east-1"
    key         = "root-password"
  }
}
```
