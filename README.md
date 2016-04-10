# SSHD Docker Image

[![GitHub license](https://img.shields.io/github/license/ourtownrentals/docker-sshd.svg)](./LICENSE.txt)

## Description

Minimal Alpine Linux Docker container
with `sshd` exposed and `rsync` installed.
Based on [macropin/docker-sshd](https://github.com/macropin/docker-sshd)
by Andrew Cutler.

## Usage

### Requirements

- [Docker].

The images are built and hosted automatically on Docker Hub
at [ourtownrentals/sshd].

Pull with

```
$ docker pull ourtownrentals/sshd
```

Mount your .ssh credentials (RSA public keys) at `/root/.ssh/`
in order to access the container via root ssh.

Optionally mount a custom sshd config at `/etc/ssh/`.

```
docker run -d -p 2222:22 \
  -v /secrets/id_rsa.pub:/root/.ssh/authorized_keys:ro \
  -v /mnt/data/:/data/ ourtownrentals/sshd
```

[Docker]: https://www.docker.com/
[ourtownrentals/sshd]: https://hub.docker.com/r/ourtownrentals/sshd/

## Development and Testing

### Source Code

The [sshd source] is hosted on GitHub.
Clone the project with

```
$ git clone https://github.com/ourtownrentals/docker-sshd.git
```

[sshd source]: https://github.com/ourtownrentals/docker-sshd

### Testing Locally

Build and run the container with

```
$ docker build -t sshd .
$ docker run sshd
```

## Contributing

Please submit and comment on bug reports and feature requests.

To submit a patch:

1. Fork it (https://github.com/ourtownrentals/docker-sshd/fork).
2. Create your feature branch (`git checkout -b my-new-feature`).
3. Make changes.
4. Commit your changes (`git commit -am 'Add some feature'`).
5. Push to the branch (`git push origin my-new-feature`).
6. Create a new Pull Request.

## License

This app is licensed under the MIT license.

## Warranty

This software is provided "as is" and without any express or
implied warranties, including, without limitation, the implied
warranties of merchantibility and fitness for a particular
purpose.
