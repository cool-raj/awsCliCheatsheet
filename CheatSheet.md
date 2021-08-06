# List aws users in a account:

 # _Usage : list all the user with match like 'gitlab' with case insensitive output as json ._

__Eg__: aws iam list-users | jq  '.Users[] | select(.UserName | match(["GITLAB", "i"]))'

# _Usage : list all the userName from the list of users with match like 'gitlab' with case insensitive output as text._

__Eg__: aws iam list-users | jq -r '.Users[] | select(.UserName | match(["GITLAB", "i"]))' | jq -r '.UserName'

 # _Usage : list all the ecr repositories in a account.
__Eg__: aws ecr describe-repositories | jq   '.repositories[].repositoryName'

# _Usage : list all the images in a given ecr repositories in a account.
__Eg__: aws ecr list-images --repository-name __testrepo__

 # _Usage : list all the ecs cluster in a given  account.
__Eg__: aws ecs list-clusters

# Tips
1. Use the --dryrun Flag in the AWS CLI Before Performing Any Task on Production Resources.

 ``` aws s3 cp /path/to/local/files/ s3://demo-datasets/path/ --exclude "*" --include "*.csv" --dryrun ```
 
2. Use --dryrun To Check if Two S3 buckets Are in Sync.

 ``` aws s3 sync s3://bucket1 s3://bucket2 --dryrun ```

3. Use --dryrun To Check if an S3 Bucket and a Local Folder Are in Sync

  ``` aws s3 sync /Users/.../path/ s3://mybucket --dryrun ```
  
4. Download/upload Files recursively to/From S3


   ``` aws s3 cp s3://mybucket /Users/anna/path/ --recursive --storage-class STANDARD ```
   ``` aws s3 cp /Users/.../path/ s3://mybucket  --recursive --storage-class STANDARD ```
  

