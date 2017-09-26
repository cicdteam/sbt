# sbt in docker

# usage

Compilation of your scala based project

```
docker run \
    --name sbt-onbuild \
    --rm \
    --volume "$HOME"/.ivy2:"$HOME"/.ivy2 \
    --volume "$HOME"/.sbt:"$HOME"/.sbt \
    --volume "$PWD":/project \
    --volume /etc/passwd:/etc/passwd:ro \
    --user $(id -u):$(id -g) \
    --workdir /project \
    pure/sbt package
```
