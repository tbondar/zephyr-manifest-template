# Zephyr Manifest Template

## Python virtual environment
```
$ mkdir zephyr-application
$ python -m venv zephyr-application/.venv
$ source zephyr-application/.venv/bin/activate
$ python -m pip install west
```

## Initialise and install workspace

### Using Remote Repository

```
$ cd zephyr-application
$ west init -m git@github.com:tbondar/zephyr-manifest-template.git .
```

### Using Local repository

```
$ cd zephyr-application
$ west init --local app
```

## Finish installing workspace

```
$ west update
$ west zephyr-export
$ python -m pip install -r deps/zephyr/scripts/requirements.txt
```

## Build
```
$ west build -b nucleo_f042k6 app
```

Resulting directory tree.
```
zephyr-application/
  ∟ app/
  ∟ build/
  ∟ deps/
```

## References

### Articles
[Manifests: Project Sanity in the Ever-Changing Zephyr World](https://blog.golioth.io/manifests-project-sanity-in-the-ever-changing-zephyr-world/)
[Improving Zephyr Project Structure with Manifest Files](https://blog.golioth.io/improving-zephyr-project-structure-with-manifest-files/)
[How to build your Zephyr app in a standalone folder](https://blog.golioth.io/how-to-build-your-zephyr-app-in-a-standalone-folder/)

### Documentation
[iWest Manifests](https://docs.zephyrproject.org/3.5.0/develop/west/manifest.html)

### Examples

[Golioth Zephyr Training](https://github.com/golioth/zephyr-training)
