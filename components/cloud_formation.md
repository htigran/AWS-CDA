# Cloud Formation

* Allows us to deploy resources through a json template
* the template can build a complete stack
* stack is set of resources that are created and managed as a single unit when cloud formation instantiated a template
* the AWS resources which are a part of the stack can be individually managed
* the template json has 5 types of elements
	* parameters optional
	* outputs optional
	* list of data tables optional
	* list of resources
	* template file format version number
* Sections: Resources, Parameters, Outputs, AWSTemplateFormatVersion, Description, Mappings
* Resources section in the template is the only thing required for it to work
* Fn::GetAtt returns a value for the specified attribute
* If error happens, then a rollback takes place. However charges may apply for the time the resources were created
* cfn-list-stacks : lists all current stacks in your cloud formation
* template description cannot be added if AWSTemplateFormatVersion is not declared at the top
* deletion policy can be specified, and snapshots can be taken before deletion
* stack can be modified after creation
* stacks can be created in VPC
* Limits
	* there are no limits on number of templates
	* Template, parameters, output and resource description are limited to 4096 characters
	* you can have 60 parameters and 60 outputs in a template
	* Each cloudformation account is limited to 20 stacks. Can be increased by contacting AWS via form
	* cloud formation access point url https://cloudformation..amazonaws.com
