# ps4-waker-rest

This is simple REST-wrapper around [ps4-waker](https://github.com/dhleong/ps4-waker). Used for Samsung SmartThings

**Warning**: no authentication is performed. Don't expose this service to outside network.

For amd32/64

Run this image:
`docker run -d --restart always --name ps4waker -v "/path/to/your/config/folder:/waker/data" --net=host xtreme22886/ps4-waker-rest`

For arm32 (Raspberry Pi)

Run this image:
`docker run -d --restart always --name ps4waker -v "/path/to/your/config/folder:/waker/data" --net=host xtreme22886/ps4-waker-rest-arm`

1. Open Docker app in Synology Web GUI
2. Select the Registry tab in the left menu
3. Search for "xtreme22886"
4. Select and download the "xtreme22886/unifi-presence-rest" image (choose the "latest" tag for the stable version or see the Docker Versions section above for other versions/tags)
5. Select the Image tab in the left menu and wait for the image to fully download
6. Select the downloaded image and click on the Launch button
7. Give the Container a sensible name (e.g. "unifi-presence")
8. Click on Advanced Settings
9. Check the "auto-restart" checkbox in the Advanced Settings tab
10.  Check the "Use the same network as Docker Host" checkbox in the Network tab
11. Click on Apply => Next => Apply

The REST wrapper around ps4-waker will listen on port `3031` by default. If you encounter any port conflicts run the container with the port option: `-p XXXX:3031`
