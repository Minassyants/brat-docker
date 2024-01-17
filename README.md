Adding docker-compose file for easy setup using the pre-built image hosted by cassj/brat-docker

### Usage

1. if running in localhost, just create two folders: brat-data, brat-cfg
```
|-- brat-cfg
|   `-- users.json
|-- brat-data
```
2. create users.json file inside brat-cfg with the following: (this will hold user authentication in plaintext)
```
{
    "user1":"pass1",
}
```
3. make sure to adjust right folder and ownership permissions to `brat-data` folder, as this will be used by `www-data` user inside the container, to add/edit annotations from local as well, issue the following commands:
```
sudo chown -R www-data:www-data brat-data
sudo chmod -R 777 brat-data
```
4. pull and run the service: `sudo docker compose up -d` server will be accessible at: `localhost:80`
