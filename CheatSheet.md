# List aws users in a account:
 # _Usage : list all the user with match like 'gitlab' with case insensitive._

__Eg__: aws iam list-users | jq  '.Users[] | select(.UserName | match(["GITLAB", "i"]))'
