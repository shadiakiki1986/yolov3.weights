# yolov3.weights

A repo just to host the yolov3.weights file from https://pjreddie.com/darknet/yolo/ in the repo releases for the sake of faster download time

## Usage

Instead of

```
# several minutes on colab
wget https://pjreddie.com/media/files/yolov3.weights
```

Use

```
# 15 seconds on colab
wget https://github.com/shadiakiki1986/yolov3.weights/releases/download/3.0.1/yolov3.weights
```

## Dev notes

To create a new release from the command line

1. Install github cli

```
tgz_ghcli = "gh_1.4.0_linux_amd64.tar.gz"
!wget https://github.com/cli/cli/releases/download/v1.4.0/$tgz_ghcli
!tar -xzf "$tgz_ghcli"
!rm "$tgz_ghcli"
!ln -s /content/gh_1.4.0_linux_amd64/bin/gh /usr/local/bin/gh
```

2. Create a personal access token in github settings, then save to file

```
!echo "abc123..." > mytoken.txt
```

3. login with github cli

```
!gh auth login --with-token < mytoken.txt
```

4. Create a release and upload the asset

```
!gh release create --repo shadiakiki1986/yolov3.weights --title "3.0.1" --notes "3.0.1" 3.0.1
!gh release upload --repo shadiakiki1986/yolov3.weights 3.0.1 darknet/yolov3.weights
```
