# CloudFormation

## Core Concepts 
- [ ] Templates
- [ ] Stacks
- [ ] Change Sets 

## Setting Up
- [ ] Quotas
- [ ] Endpoints
- [ ] AWS SDKs

## Getting Started 

AWS CloudFormation makes deploying a set of Amazon Web Services (AWS) resources as simple as submitting a template. A `template` is a text file that describes a `stack`, a collection of AWS resources you want to deploy together as a group. You use the template to define all the AWS resources you want in your stack. This can include Amazon Elastic Compute Cloud instances, Amazon Relational Database Service DB Instances, and other resources.  `parameters` can aslo be used within the `stack` to enable you to pass in specific values when you create a stack from a template. `Change Sets` are methods to handle modifications to your `stack`. Instead of delete and redeploying a stack, a `change set` can be used to modify a deployed `stack` configuration. For a list of resource types compatible with AWS CloudFormation, see [here](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)

### Template [docs](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/gettingstarted.templatebasics.html)

A template is a declaration of the AWS resources that make up a stack. The template is stored as a text file whose format complies with the JavaScript Object Notation (JSON) or YAML standard. Because they're text files, you can create and edit them in any text editor and manage them in your source control system with the rest of your source code. In the template, you declare the AWS resources you want to create and configure. You declare an object as a name-value pair or a pairing of a name with a set of child objects enclosed.

A template includes six top-level sections: 
1. AWSTemplateFormatVersion, 
2. Description, 
3. Parameters, 
4. Mappings, 
5. Resources, 
6. and Outputs however, only the **Resources** section is required.

You use the `Parameters` section to declare values that can be passed to the template when you create the stack. A parameter is an effective way to specify **sensitive information**, such as `user names and passwords`, that you _don't want to store in the template itself_. It's also a way to specify information that **might be unique to the specific application or configuration** you are deploying, for example, `a domain name or instance type`.

The Ref function returns the value of the object it refers to.
 - the Ref function can be used to set a value
 - the Ref function can also set a resource's property to the value of another resource

You use `mappings` to declare conditional values that are evaluated in a similar manner as a look up table statement. Outputs define custom values that are returned by the aws cloudformation describe-stacks command and in the CloudFormation console Outputs tab after the stack creation. You can use output values to return information from the resources in the stack, such as the URL for a website that was created in the template.