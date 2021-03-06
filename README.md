# CircleCI Server Setup

This package allows you to orchestrate your CircleCI Server cluster in AWS using Terraform.

**Note: This is only meant to be used for the initial setup of CircleCI Server and is not meant to be used for the ongoing maintenance of the CircleCI Server.**

**Note: Master is the only supported branch. All other branches of this repo should not be considered stable, and is to be used at your own risk.**

## Prerequisites and Requirements

Please refer to our prerequisites documentation here: https://circleci.com/docs/2.0/aws-prereq.

## Installation

You can find instructions here: https://circleci.com/docs/2.0/aws/.

### Variables

There are some optional variables that aren't described in the instructions.
You can view their names and descriptions in [variables.tf](variables.tf).

  | Var      | Description | Default |
  | -------- | ----------- | ------- |
  | services_instance_type | Instance type for the centralized services box.  We recommend a m5 instance | m5.2xlarge |
  | builder_instance_type | Instance type for the 1.0 builder machines.  We recommend a r5 instance | r5.2xlarge |
  | max_builders_count | Max number of 1.0 builders | 2 |
  | nomad_client_instance_type | Instance type for the nomad clients (2.0 builders). We recommend a m5 instance | m5.2xlarge |
  | max_clients_count | Max number of nomad clients | 2 |
  | prefix   | Prefix for resource names | circleci |
  | enable_nomad | Provisions a nomad cluster for CCIE v2 | 1 |
  | enable_route | Enable creating a Route53 route for the Services box | 0 |
  | enable_govcloud | Allows deployment into AWS GovCloud | false |
  | route_name | Route name to configure for Services box | "" |
  | route_zone_id | Zone to configure route in | "" |
  | services_user_data_enabled | Enable/disable automated installation on Services Box | true |
  | force_destroy_s3_bucket | Add/Remove ability to forcefully destroy S3 bucket | false |
  | services_disable_api_termination | Protect the services instance from API termination | true |


### Teardown

You can find teardown instructions at https://circleci.com/docs/2.0/aws-teardown/.

## Upgrade

If you want to upgrade an existing installation from a previous version, follow these [upgrade instructions](https://circleci.com/docs/2.0/updating-server/#section=server-administration).
