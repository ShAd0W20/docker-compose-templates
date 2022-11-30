# Apache

This is a simple Apache image that can be used to serve static content.

## Usage

Copy the `docker-compose.yaml` file to your project

If you check the `docker-compose.yml` file you will see that it's copying a folder named `website` folder to the container. This is the folder that will be served by Apache.

You can change the folder name to whatever you want, but you will need to change the `docker-compose.yaml` file to reflect that.

To use this image, you can run the following command:

```bash
docker-compose -f docker-compose.yaml up -d
```
