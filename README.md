# practice-caddy-nested

A practice of Caddyfile for root -> middle -> app nested caddy servers.

## structure

- [root](root)
    - listen :9000
    - proxy requests for `/middle` to :9001
- [middle](middle)
    - listen :9001
    - proxy requests for `/app` to :9002
- [app](app)
    - listen :9002

After you execute `caddy` on each directories, you might request

- http://localhost:9000/middle/app
- http://localhost:9001/app
- http://localhost:9002/

to get [app/index.html](app/index.html).
