#list aws Users in a account:
aws iam list-users | jq  '.Users[] | select(.UserName | match(["GITLAB", "i"]))'
