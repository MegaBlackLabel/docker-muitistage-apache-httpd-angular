# docker-muitistage-apache-httpd-angular

# Develop(start ng server)

## build
```
docker-compose build
```

## start
```
docker-compose up -d
```

## down
```
docker-compose -f down -v
```


# Production(create docker image)

## build
```
docker-compose -f ./prod/docker-compose.yml build
```

## start
```
docker-compose -f ./prod/docker-compose.yml up -d
```

## down
```
docker-compose -f ./prod/docker-compose.yml down -v
```