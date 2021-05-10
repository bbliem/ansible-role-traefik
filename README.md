# ansible-traefik

Ansible role for Traefik 2

## Variables

* `traefik_acme_email` [required]: Email address used for Let's Encrypt certificates
* `traefik_config_dir` [default: `/usr/local/etc/traefik`]: Directory on the host containing traefik configuration and ACME certificates
* `traefik_dashboard_basic_auth_users` [required only if `traefik_debug` is true]: String specifying login details for the dashboard. Can be generated with `htpasswd -nb <user> <password>`.
* `traefik_dashboard_router_rule` [required only if `traefik_debug` is true]: Traefik router rule for accessing the dashboard. Example: ``Host(`example.com`) && (PathPrefix(`/api`) || PathPrefix(`/dashboard`))``
* `traefik_debug` [default: `false`]: If `true`, traefik will print debug messages, and the API and dashboard will be enabled
* `traefik_docker_image` [default: `traefik:latest`]: Image of the traefik docker image to use
* `traefik_networks` [required]: List of names of docker networks that traefik should watch
