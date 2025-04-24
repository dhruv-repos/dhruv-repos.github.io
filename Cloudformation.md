---
title: AWS Cloudformation
layout: default
---
# AWS Cloudformation
## Infrastructure as Code IaC
Infrastructure as Code (IaC) is the managing and provisioning of infrastructure through code instead of through manual processes.
With IaC, configuration files are created that contain your infrastructure specifications, which makes it easier to edit and distribute configurations.
## Sections in Cloud Front template
- Resources : required top-level section in a CloudFormation template. It declares the AWS resources that you want CloudFormation to provision and configure as part of your stack.
```yaml
{
Resources:
  LogicalResourceName1:
    Type: AWS::ServiceName::ResourceType
}

```
- Parameters : You can input custom values to your template each time you create or update a stack.  The only required attribute is ```Type```, which can be String, Number, or a CloudFormation-supplied parameter type
- Output : declares output values for the stack.
- Mapping : The optional Mappings section helps you create key-value pairs that can be used to specify values based on certain conditions or dependencies.