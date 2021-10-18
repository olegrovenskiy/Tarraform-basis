# Tarraform-basis

# 7.3. Основы и принцип работы Терраформ

##  Задача 1. Создадим бэкэнд в S3

Создал в AWS S3 bucket и папку

https://c2n.me/4dGCJYc

![bucket](https://github.com/olegrovenskiy/Tarraform-basis/blob/main/bucket.png)

прописал в файле конфигурации

    terraform {
      backend "s3" {
      bucket = "bucket-net"
      key    = "oleg/net-hw/terraform.tfstate"
      region = "eu-central-1"
     }
    }

Результат команд init & plan


    c:\Oleg\terraform3>terraform init -reconfigure
    
    Initializing the backend...
    
    Successfully configured the backend "s3"! Terraform will automatically
    use this backend unless the backend configuration changes.
    
    Initializing provider plugins...
    - Finding latest version of hashicorp/aws...
    - Installing hashicorp/aws v3.63.0...
    - Installed hashicorp/aws v3.63.0 (signed by HashiCorp)
    
    Terraform has created a lock file .terraform.lock.hcl to record the provider
    selections it made above. Include this file in your version control repository
    so that Terraform can guarantee to make the same selections by default when
    you run "terraform init" in the future.
    
    Terraform has been successfully initialized!
    
    You may now begin working with Terraform. Try running "terraform plan" to see
    any changes that are required for your infrastructure. All Terraform commands
    should now work.
    
    If you ever set or change modules or backend configuration for Terraform,
    rerun this command to reinitialize your working directory. If you forget, other
    commands will detect it and remind you to do so if necessary.
    
    c:\Oleg\terraform3>terraform plan
    
    Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the
    following symbols:
      + create
    
    Terraform will perform the following actions:
    
     # aws_instance.Netology-HWork will be created
     + resource "aws_instance" "Netology-HWork" {
         + ami                                  = "ami-0c36ff844020f5a8b"
         + arn                                  = (known after apply)
         + associate_public_ip_address          = (known after apply)
         + availability_zone                    = (known after apply)
         + cpu_core_count                       = (known after apply)
         + cpu_threads_per_core                 = (known after apply)
         + disable_api_termination              = (known after apply)
         + ebs_optimized                        = (known after apply)
         + get_password_data                    = false
         + host_id                              = (known after apply)
         + id                                   = (known after apply)
         + instance_initiated_shutdown_behavior = (known after apply)
         + instance_state                       = (known after apply)
         + instance_type                        = "t2.micro"
         + ipv6_address_count                   = (known after apply)
         + ipv6_addresses                       = (known after apply)
         + key_name                             = (known after apply)
         + monitoring                           = (known after apply)
         + outpost_arn                          = (known after apply)
         + password_data                        = (known after apply)
         + placement_group                      = (known after apply)
         + placement_partition_number           = (known after apply)
         + primary_network_interface_id         = (known after apply)
         + private_dns                          = (known after apply)
         + private_ip                           = (known after apply)
         + public_dns                           = (known after apply)
         + public_ip                            = (known after apply)
         + secondary_private_ips                = (known after apply)
         + security_groups                      = (known after apply)
         + source_dest_check                    = true
         + subnet_id                            = (known after apply)
         + tags                                 = {
             + "Name" = "Netol-HW-Test"
            }
         + tags_all                             = {
             + "Name" = "Netol-HW-Test"
           }
         + tenancy                              = (known after apply)
         + user_data                            = (known after apply)
         + user_data_base64                     = (known after apply)
         + vpc_security_group_ids               = (known after apply)
    
         + capacity_reservation_specification {
             + capacity_reservation_preference = (known after apply)
    
             + capacity_reservation_target {
                 + capacity_reservation_id = (known after apply)
                }
            }
    
          + ebs_block_device {
              + delete_on_termination = (known after apply)
              + device_name           = (known after apply)
              + encrypted             = (known after apply)
              + iops                  = (known after apply)
              + kms_key_id            = (known after apply)
              + snapshot_id           = (known after apply)
              + tags                  = (known after apply)
              + throughput            = (known after apply)
              + volume_id             = (known after apply)
              + volume_size           = (known after apply)
              + volume_type           = (known after apply)
           }
    
          + enclave_options {
             + enabled = (known after apply)
            }
    
          + ephemeral_block_device {
              + device_name  = (known after apply)
              + no_device    = (known after apply)
              + virtual_name = (known after apply)
           }
    
         + metadata_options {
             + http_endpoint               = (known after apply)
             + http_put_response_hop_limit = (known after apply)
             + http_tokens                 = (known after apply)
            }
    
         + network_interface {
              + delete_on_termination = (known after apply)
              + device_index          = (known after apply)
              + network_interface_id  = (known after apply)
            }
    
         + root_block_device {
             + delete_on_termination = (known after apply)
             + device_name           = (known after apply)
             + encrypted             = (known after apply)
             + iops                  = (known after apply)
             + kms_key_id            = (known after apply)
             + tags                  = (known after apply)
             + throughput            = (known after apply)
             + volume_id             = (known after apply)
             + volume_size           = (known after apply)
             + volume_type           = (known after apply)
           }
        }
    
    Plan: 1 to add, 0 to change, 0 to destroy.
        
    ───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
    
    Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if
    you run "terraform apply" now.
    
Обе команды прошли успешно

##  Задача 2


