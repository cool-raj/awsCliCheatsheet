# List aws users in a account:

 # _Usage : list all the user with match like 'gitlab' with case insensitive output as json ._

__Eg__: aws iam list-users | jq  '.Users[] | select(.UserName | match(["GITLAB", "i"]))'

# _Usage : list all the userName from the list of users with match like 'gitlab' with case insensitive output as text._

__Eg__: aws iam list-users | jq -r '.Users[] | select(.UserName | match(["GITLAB", "i"]))' | jq -r '.UserName'
