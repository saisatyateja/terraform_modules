### example module Templete
-----------------------------
```
module "vpc_subnets" {
  source = "github.com/saisatyateja/terraform_modules"

  vpc_details = {
    cidr = "10.0.0.0/21"
    name = "ohio_vpc"
  }
  subnet_details = {
    az = ["us-east-2a","us-east-2a","us-east-2b","us-east-2b","us-east-2c","us-east-2c"]
    names = ["db1","app1","web1","db2","app2","web2"]
  }
}
output "my_vpc_id" {
  value = module.vpc_subnets.vpc_id
}
output "subnet_count_from_module" {
  value = module.vpc_subnets.subnets_count
}
```