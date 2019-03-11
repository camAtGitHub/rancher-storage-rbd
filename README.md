My Fork - 2019
==============
This fork has updated 'rancher/storage-rbd' to include support for Ceph v12, it also includes support for ceph usernames to mount the images/pool with.  
  
These plugins are designed for Rancher 1.6.x

## Bugs

Not a bug of mine, but I suspect with 'rbd' when you stop the 'stack' Rancher is producing the events:
`11/03/2019 14:11:49time="2019-03-11T04:11:49Z" level=info msg=unmount.request name="VOLUMENAME_HERE"
11/03/2019 14:11:49time="2019-03-11T04:11:49Z" level=info msg=unmount.response name="VOLUMENAME_HERE"`

But the rbd device never gets unmounted, even though the stack is stopped. Although the volume will get unmounted etc in a failover / follow-host-container event. Just seems this situation is not catered for.  

I suspect the issue lies in `docker/volumeplugin/plugin.go` unmount code.

Rancher Storage
==============

This repo contains Rancher specific storage plugins

## Building

`make`
This will create docker images with tag 'dev' on your host


## Running

Add this repo as a catalog in Rancher to run the local builds

## License
Copyright (c) 2014-2016 [Rancher Labs, Inc.](http://rancher.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

## Installation
Avoid all the building and import the git repo https://github.com/camAtGitHub/rancher-rbd-catalog (https://github.com/camAtGitHub/rancher-rbd-catalog.git) into a Rancher-Catalog - Then just click install the storage-driver.  
Images hosted at: https://hub.docker.com/r/camboatdocker/rancher-storage-rbd
