# Deploy AWS ElasticBeanstalk app with CloudFormation template

1. Create a EC2 key pair: EC2 > Key pairs > Create key pair.

2. Generate the CloudFormation template.

    `aws cloudformation package --s3-bucket <s3-bucket> --template-file elasticBeanstalkTemplate.yml --output-template-file template-generated.yml`

3. Deploy the CloudFormation template.

    `aws cloudformation deploy --template-file template-generated.yml --stack-name sampleNodeApp --parameter-overrides KeyName=<KeyName> --capabilities CAPABILITY_IAM`