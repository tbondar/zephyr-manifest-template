# Zephyr Manifest Template

## Install `west`

Create a directory for your new Zephyr application and set up a Python virtual environment in it.
```
$ mkdir zephyr-application
$ python -m venv zephyr-application/.venv
$ source zephyr-application/.venv/Scripts/activate
```

Install `west`.
```
$ python -m pip install west
```

## Create a `west` workspace

You can do this by cloning this repository to your application directory.

```
$ cd zephyr-application
$ west init -m https://github.com/tbondar/zephyr-manifest-template.git .
```

Alternatively you can download a ZIP of this repository and unpack it in your application directory. Rename it to `app` and use it to create your workspace.

```
$ cd zephyr-application
$ unzip ~/Downloads/zephyr-manifest-template-main.zip
$ mv zephyr-manifest-template-main app
$ west init --local app
```

## Finish creating your workspace

```
$ west update
$ west zephyr-export
$ python -m pip install -r deps/zephyr/scripts/requirements.txt
```

## Build the sample application

Before building the application you have to install the Zephyr SDK as described [here](https://docs.zephyrproject.org/latest/develop/getting_started/index.html#install-the-zephyr-sdk)

```
$ west build -b nucleo_f042k6 app
```

Resulting directory tree.
```
zephyr-application/
│
├── app/
├── build/
└── deps/
```

## References

### Articles
- [Manifests: Project Sanity in the Ever-Changing Zephyr World](https://blog.golioth.io/manifests-project-sanity-in-the-ever-changing-zephyr-world/)
- [Improving Zephyr Project Structure with Manifest Files](https://blog.golioth.io/improving-zephyr-project-structure-with-manifest-files/)
- [How to build your Zephyr app in a standalone folder](https://blog.golioth.io/how-to-build-your-zephyr-app-in-a-standalone-folder/)

### Documentation
[West Basics](https://docs.zephyrproject.org/3.5.0/develop/west/basics.html)
[West Manifests](https://docs.zephyrproject.org/3.5.0/develop/west/manifest.html)

### Examples
[Golioth Zephyr Training](https://github.com/golioth/zephyr-training)
