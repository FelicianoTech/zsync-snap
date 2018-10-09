# zsync Snap Package [![CircleCI Build Status](https://circleci.com/gh/felicianotech/zsync-snap.svg?style=shield)](https://circleci.com/gh/felicianotech/zsync-snap) [![GitHub License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/felicianotech/zsync-snap/master/LICENSE)

`zsync` is a file transfer program. It allows you to download a file from a remote server, where you have a copy of an older version of the file on your computer already. zsync downloads only the new parts of the file. It uses the same algorithm as rsync. However, where rsync is designed for synchronising data from one computer to another within an organisation, zsync is designed for file distribution, with one file on a server to be distributed to thousands of downloaders. zsync requires no special server software — just a web server to host the files — and imposes no extra load on the server, making it ideal for large scale file distribution.

This repository provides the source code for the `zsync` snap which is available in the [Snapcraft Store](https://snapcraft.io/zsync).
The snap is maintained by [@FelicianoTech](https://twitter.com/FelicianoTech) meanwhile the code for `zsync` itself is maintained by [Colin Phipps](http://zsync.moria.org.uk).
The upstream repository can be found [here](https://github.com/cph6/zsync).


## Installation

`zsync` can be installed via snap on Ubuntu 16.04, Ubuntu 18.04+, and many Linux distros with `snapd` installed  by running:

```
sudo snap install zsync
```

If you don't have the `snap` command available, you might be able to find instructions for your distro [here](https://docs.snapcraft.io/core/install).
`zsync` might also be available via your distro's package manager.


## Usage

```
zsync <zsync-file-url>
```

Where `<zsync-file-url` is a HTTP URL to a zsync file provided somewhere.

For example, I like to keep up with the development of Ubuntu's upcoming release since they provide daily images.
Right now, I periodicly run the following commands on my laptop in order to sync the latest daily build of Ubuntu Cosmic (which will eventually be Ubuntu 18.10):

```bash
cd ~/Downloads/disk-images && zsync http://cdimage.ubuntu.com/daily-live/current/cosmic-desktop-amd64.iso.zsync
```


## Development

This snap can be built with Snapcraft.
On Ubuntu:


```
sudo snap install --classic snapcraft
snapcraft snap
```


## License

The code for this snap is licensed under the MIT license.
The code for `zsync` itself is licensed under the Artistic License.
This repo's license can be found [here](./LICENSE) while the license for `zsync` can be found [here](https://github.com/cph6/zsync/blob/master/c/COPYING).
