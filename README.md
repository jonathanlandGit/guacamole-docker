# guacamole

Basic guacamole single container server. 

To get this started, just edit a couple of files and copy them into storage/guacamole folder

For example, 

```bash
git clone https://github.com/jonathanland/guacamole.git
cd guacamole
mkdir -p storage/guacamole
cp ./guacamole.properties storage/guacamole
cp ./user-mapping.xml storage/guacamole
docker build --tag guacamole .
```
Use an editor to /storage/guacamole/user-mapping.xml and all the hosts to access. 
You can use this example for documentation to edit the file: [Guacamole](https://guacamole.apache.org/doc/gug/configuring-guacamole.html) 

Now, just start the container:

```bash
docker run -d --name guacamole -p 8080:8080 -v /storage/guacamole:/app/guacamole	 guacamole 
```

NOTE: For docker run on mac, you may need to allow file sharing via docker desktop and then put the relative path to the properties and mapping files, like this.
```bash
docker run -d --name guacamole -p 8080:8080 -v /Users/jonathanland/Desktop/guacamole/storage/guacamole:/app/guacamole guacamole 
```

You should be able to connect to your guacamole server on port 8080.

```
http://localhost:8080
```

To modify your connections just edit your /storage/guacamole/user-mapping.xml logoff and log back in to your guacamole server. 











