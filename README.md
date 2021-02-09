# SBIR-FAIR


```bash
git clone --recurse-submodules --depth 1 git@github.com:sbi-fair/sbi-fair.github.io.git
cd sbir-fair
npm install
hugo server
```

## Running a container locally

You can run docsy-example inside a [Docker](ihttps://docs.docker.com/)
container, the container runs with a volume bound to the `docsy-example`
folder. This approach doesn't require you to install any dependencies other
than Docker.

1. Build the docker image 

```bash
docker build -f dev.Dockerfile -t docsy-example-dev:latest .
```

1. Run the built image

```bash
docker run --publish 1313:1313 --detach --mount src="$(pwd)",target=/home/docsy/app,type=bind docsy-example-dev:latest
```

Open your web browser and type `http://localhost:1313` in your navigation bar,
This opens a local instance of the docsy-example homepage. You can now make
changes to the docsy example and those changes will immediately show up in your
browser after you save.

To stop the container, first identify the container ID with:

```bash
docker container ls
```

Take note of the hexadecimal string below the `CONTAINER ID` column, then stop
the container:

```bash
docker stop [container_id]
```

To delete the container run:

```
docker container rm [container_id]
```
