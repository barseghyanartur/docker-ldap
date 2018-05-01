# Simple Basic apache auth with LDAP

- Uses Apache's `authnz_ldap` module to set up LDAP auth in a Docker container.
- LDAP credentials are passed in via environment variable during the run command. 

Build the image:
```$xslt
docker build \
    -t docker-ldap \
    -f ./Docker/dockerfile \
    .
```

Run the container entering your LDAP account credentials:
```$xslt
docker run \
    -p 3000 \
    -n ldap_demo \
    -e LDAP_BIND_ON='"CN=example,OU=example,DC=example"' \
    -e LDAP_PASSWORD='"my_ldap_password"' \
    -e LDAP_URL='"my_ldap_url"' \
    docker-ldap
```

[Visit the demo page](http://localhost:3000/demo) and use you active directory name:password to access the site.