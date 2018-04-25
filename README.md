# README

dokku apps:create vcbc
dokku postgres:create vcbc_db
dokku postgres:link vcbc_db vcbc

DATABASE_URL:  postgres://postgres:f734e7e24447e8e7180e1c9aefca3e64@dokku-postgres-vcbc-db:5432/vcbc_db

# create user and add user to sudo group

adduser deploy
usermod -aG sudo deploy

or

adduser deploy sudo

# switch user
su - deploy

# Run ‘sudo’ Command Without Entering a Password

open /etc/sudoers
add this line
deploy ALL=(ALL) NOPASSWD: ALL

# create authorized_keys
mkdir .ssh
chmod 700 .ssh
touch .ssh/authorized_keys
chmod 600 .ssh/authorized_keys
