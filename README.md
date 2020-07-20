# Phalcon + Rector in docker
Docker containers with Phalcon and Rector installed for easily scanning your project.

**Installation**
This is an unusual set up, just run the commands below in your project directory and the required containers will be pulled, once this is done, you can then use Rector outside the container, with the respective commands below. 

Create a `rector.yml` file in the root of your project containing the directories that need to be scanned and the directories that need to be autoloaded.

For example:
```
parameters:
  paths:
    - 'app'
    - 'public'
  autoload_paths:
    - 'app'
```

**Phalcon 3.4 -> Phalcon 4**

Run inside your project:

Linux:
```
docker run -v $(pwd):/project ruudboon/phalcon-rector:php73-v3_to_v4
```
Mac:
```
docker run -v "$(pwd):/project" ruudboon/phalcon-rector:php73-v3_to_v4
```

You will get an overview of suggested changes.
If you want to apply these changes by rector run:

Linux:
```
docker run -v $(pwd):/project ruudboon/phalcon-rector:php73-v3_to_v4 process --set phalcon40
```
Mac: 
```
docker run -v "$(pwd):/project" ruudboon/phalcon-rector:php73-v3_to_v4 process --set phalcon40
```

**PHP 7.4 - Phalcon 4**

Need to check if your interfaces align and you are 7.4 compatible? 

Linux:
```
docker run -v $(pwd):/project ruudboon/phalcon-rector:php74-v4 process --set php74
```
Mac:
```
docker run -v "$(pwd):/project" ruudboon/phalcon-rector:php74-v4 process --set php74
```
