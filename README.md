#!/bin/bash

# create directories for different file types
mkdir -p images documents music videos

# move files to the appropriate directory based on their extension
case $1 in
    *.png|*.jpeg|*.jpg)
        mv $1 images/
        ;;
    *.doc|*.pdf|*.txt)
        mv $1 documents/
        ;;
    *.mp3|*.wav)
        mv $1 music/
        ;;
    *.mp4|*.avi|*.mkv)
        mv $1 videos/
        ;;
    *)
        echo "Unknown file type"
        ;;
esac

# cross-compile C code for ARM architecture
arm-linux-gnueabihf-gcc -o hello_arm hello.c
