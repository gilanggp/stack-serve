


Before starting the service 

##Create user first 

# Generate admin user
docker run -it --rm amir20/dozzle generate admin --password ur-super-secret-pass --email admin@exam.com --name "admin" --user-roles admin > .users.yaml

# Append viewer user
docker run -it --rm amir20/dozzle generate viewer --password ur-super-secret-pass --email viewer@exam.com --name "viewer" --user-roles viewer >> .users.yaml

##Remove invalid duplication "users:" in .users.yaml 

sed '8d' .users.yaml > users.yaml && mv users.yaml .users.yaml

this will remove 8th line in .users.yaml just run it one time !
