# Docker HAProxy

Ease development with Docker by routing requests to your development domains to the right container, similarly to virtual hosts in Apache and NGINX.

## Usage

### First time set-up

1. Create a docker network named proxy: `docker network create proxy`
2. Run docker-haproxy with `docker-compose up`

### Configure your containers/services
2. Add  `VIRTUAL_HOST` environment variable to your container/service with your desired domain name (e.g. test.dev)
3. Add your domain name to your hosts file and point it to `127.0.0.1` or use [dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) route your whole TLD (e.g. .dev) to `127.0.0.1`.
4. Start your container/service and browse to your domain, voilà.

*Note: docker-haproxy only needs to be started once! After that it will automatically start whenever your docker daemon is started, even after a reboot. To stop docker-haproxy simply run `docker-compose stop`.*

## Links

* [HAProxy](http://www.haproxy.org)
* [Docker-Gen](https://github.com/jwilder/docker-gen) by Jason Wilder

## Authors

* Maarten de Boer (maarten@cloudstek.nl)

## License

BSD-2-Clause license, see [LICENSE](LICENSE)