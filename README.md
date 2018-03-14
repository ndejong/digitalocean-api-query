# digitalocean-api-query

An all-bash (+ curl) command line tool for easily making API calls to Digital 
Ocean to inspect the state of components.

Supports the following Digital Ocean (v2) API calls for query
 * [account](https://developers.digitalocean.com/documentation/v2/#account)
 * [account/keys](https://developers.digitalocean.com/documentation/v2/#ssh-keys)
 * [actions](https://developers.digitalocean.com/documentation/v2/#actions)
 * [certificates](https://developers.digitalocean.com/documentation/v2/#certificates)
 * [domains](https://developers.digitalocean.com/documentation/v2/#domains)
 * [droplets](https://developers.digitalocean.com/documentation/v2/#droplets)
 * [firewalls](https://developers.digitalocean.com/documentation/v2/#firewalls)
 * [floating_ips](https://developers.digitalocean.com/documentation/v2/#floating-ips)
 * [images](https://developers.digitalocean.com/documentation/v2/#images)
 * [load_balancers](https://developers.digitalocean.com/documentation/v2/#load-balancers)
 * [regions](https://developers.digitalocean.com/documentation/v2/#regions)
 * [sizes](https://developers.digitalocean.com/documentation/v2/#sizes)
 * [tags](https://developers.digitalocean.com/documentation/v2/#tags)
 * [volumes](https://developers.digitalocean.com/documentation/v2/#block-storage)

## Set your environment variable first
Set either `DO_TOKEN` or `TF_VAR_do_token` to your Digital Ocean API key value
before using `digitalocean-api-query` since requests all require authentication.

For example:
```bash
 $ export DO_TOKEN=122e68eac3d39a245df747f2d2a2c9c5f4c97c84e3f1463c625492cce1e622cd
```

## Example requests

obtain droplet data using 'jq' to pretty-print the response data
```
 $ digitalocean-api-query droplets | jq .
```

obtain a list of droplet.id using 'jq' to filter the response data
```
 $ digitalocean-api-query droplets | jq .droplets[].id
```

obtain a list of volume.id slugs using 'jq' to filter the response data
```
 $ digitalocean-api-query volumes | jq .volumes[].id
```

obtain a list of region slugs using 'jq' to filter the response data
```
 $ digitalocean-api-query regions | jq .regions[].slug
```


