

To run the forgejo, we need a few variables, 

1. Runner Shared Secret
2. User UUID
3. Root Password

Run the following commands to generate the values:

```
SHARED_SECRET=$(openssl rand -hex 20)
USER_UUID=$(echo -n  $SHARED_SECRET | python3 -c 'import sys; import uuid;input=sys.stdin.read();print(str(uuid.UUID(bytes=input[:16].encode("utf-8"))))')
ROOT_PASSWORD=$(openssl rand -hex 20)
echo "Runner Shared Secret: $SHARED_SECRET"
echo "User UUID: $USER_UUID"
echo "Root Password: $ROOT_PASSWORD"
```