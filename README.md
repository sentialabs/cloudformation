# Deprecated

Please see the [AWS CloudFormation Resource Specification](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-resource-specification.html) for an AWS maintained

# CloudFormation Resource Reference YAML

When you are developing a object model or a validator for CloudFormation
templates, you can surely appreciate a computer-readable specification of the
properties and return values for all CloudFormation resources.

We proudly present a YAML version of the CloudFormation
[Resource Types Reference].

We have put much effort in trying to parse the documentation as good as possible
but please keep in mind that the documentation itself may not be entirely free
of errors and inconsistencies.

## Syntax

```
---
timestamp:                       String containing the timestamp of the time
                                 parsing was finished

resources:                       Hash

  <ResourceName>:                Hash

    description:                 String containing a Markdown version of the
                                 resource documentation

    url:                         String containing the URL of the resource
                                 documentation that was parsed

    properties:                  Hash

      <PropertyName>:            Hash

        description:             String containting a Markdown version of the
                                 resource property documentation

        required:                String <(yes|no|conditional)> is the property
                                 required for the resource

        type:                    String <(
                                     String
                                   | Number
                                   | Boolean
                                   | Timestamp             # String
                                   | JSON                  # Object, not String
                                   | Hash<key: type, ...>
                                   | List<type>
                                 )>

        update_requires:         String <((no|some)_interruptions|replacement)>

    return_values:               Hash

      <(Ref|<ReturnValueName>)>: Hash

        description:             String containting a Markdown version of the
                                 resource return_value documentation
```

## Know Errors

  * Complex types are not yet parsed
  * Complex types can show up as resources

## Legal

All content of the YAML file has copyright by Amazon Web Services, Inc. or its
affiliates, and was published under the terms that can be found at
https://aws.amazon.com/terms/

[Resource Types Reference]: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
