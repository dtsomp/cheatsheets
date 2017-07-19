# Mongodb basic admin

## Console access

    mongo admin
    mongo admin -u rootadmin -p

## User management

    show users

    # ALWAYS switch to the database you need your user to be present
    use myDatabase
    db.createUser({"user":"myuser", "pwd":"mypwd", "roles": [{ role:"readWrite", db:"myDatabase"}] });

    use admin
    db.createUser({"user":"rootadmin", pwd:"rootpwd", "roles": [{ role:"root", db:"admin" }] });

    use myDatabase
    db.dropUser("nagios")

