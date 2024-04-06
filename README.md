Terraform project: Using dynamic blocks and built-in functions

###
Resource goals: Deploy an apache web server on top of an EC2 instance. Create components: VPC subnet, security group, and 3 rules within the security group. These rules will be generated using the dynamic block feature within terraform.

Next, the security group will be tied to an EC2 server bootstrapped by .sh user data script. To pass this script, the terraform code will be using built-in functions and conditional logic.

The output will be a URL of the web server to test results.
###

In the main.tf file, dynamic block is used to create ingress rules to the VPC (lines 26-34). The fileexists and file functions are used on line 53. If the fileexists function is true, then the file function is used to execute the script.

The rules for the security group are defined in variables.tf

The outputs.tf file returns the url for validation once executed.
