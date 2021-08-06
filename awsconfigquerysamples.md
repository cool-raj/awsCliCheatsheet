
SELECT
  resourceId,
  resourceType,
  awsRegion,
  resourceCreationTime,
  tags,
  configuration.state.value
WHERE
  tag.value = 'demo'
  resourceType NOT IN ('AWS::EC2::SecurityGroup',
    'AWS::EC2::Subnet', 'AWS::EC2::VPC',
    'AWS::EC2::NetworkAcl', 'AWS::EC2::RouteTable')
ORDER BY
  resourceType
