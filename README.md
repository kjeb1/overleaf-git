# overleaf-git

```
usage: overleaf-git [-h] [-m [MSG]] [-l [LINK_SHARE_URL]] [-p [PROJECT_NAME]] [command] [file [file ...]]

Add Overleaf files to Git

positional arguments:
  command               Git add|commit|download. Default: download
  file                  File(s) from Overleaf. Default: all

optional arguments:
  -h, --help            show this help message and exit
  -m [MSG], --msg [MSG]
                        Git commit message. Default: 'Commited from Overleaf'
  -l [LINK_SHARE_URL], --link-share-url [LINK_SHARE_URL]
                        Overleaf Link Share Url to Overleaf project (read)
  -p [PROJECT_NAME], --project-name [PROJECT_NAME]
                        Overleaf project name. Default: same as Git repo name

	Downloaded files from Overleaf will always OVERWRITE local files! This
	make sense because we are in a Git repo, but be careful.

        To be able to download files from Overleaf, the project need to be
        shared with the Link sharing function
        
        For first time use it will ask for the Link Share Url and store it
        in a config file within the current Git repo.

        The Overleaf project name should be the same as the Git repo name,
        but you can specify a custom Overleaf project name.

        Uses Firefox (via Selenium) to download Overleaf project Zip file.

        Firefox will access the Link Share Url, red from .overleaf-git, and 
        then get redirected to the actual project. And from there downloads
        the project Zip file. All files, or [file] [file...] will then be 
        extraced into current folder. It will detect the current Git repo 
        and git-add or git-commit.
        
        Valid options for the configfile (.overleaf-git):
        link-share-url  
        project-name 
        
        The config file is not needed if the options are provided as parameters        
 
```

Overleaf <a href="https://no.overleaf.com/learn/how-to/What_is_Link_Sharing%3F">Link Share Url</a>

## Installation
```
wget https://github.com/mozilla/geckodriver/releases/download/v0.30.0/geckodriver-v0.30.0-linux64.tar.gz
tar xzf geckodriver-v0.30.0-linux64.tar.gz
sudo mv geckodriver /usr/bin/geckodriver 
```

```
pip3 install selenium argparse gitpython cryptography
```
