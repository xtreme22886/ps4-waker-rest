# ps4-waker-rest

This is simple REST-wrapper around [ps4-waker](https://github.com/dhleong/ps4-waker). Used for Samsung SmartThings

**Warning**: no authentication is performed. Don't expose this service to outside network.

To run this image:
`docker run -d --restart always --name ps4waker -v "/path/to/your/config/folder:/waker/data" --net=host xtreme22886/ps4-waker-rest`

To generate the file `ps4-config.json` run the following commends:
1. `docker exec -it ps4waker /bin/sh`
2. `npm install -g ps4-waker`
3. `rm /waker/data/ps4-creds.json`
4. `ps4-waker -c /waker/data/ps4-creds.json`
5. Complete the pairing process and quit ps4-waker when you're done (ctrl + c).
6. Type ctrl + d to exit the container

**Note**: The container will have ps4-waker installed as long as you don't remove it. Make sure you mount a folder to `/waker/data` otherwise the credentials will be lost when you remove the container.

The REST wrapper around ps4-waker will listen on port `3031` by default. If you encounter any port conflicts run the container with the port option: `-p XXXX:3031`
