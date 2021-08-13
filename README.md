# Rusty-redis

Demo to interact with Redis using `redis-rs` client

Uses common redis data structures like String, Hash, List
using low and high level APIs

uses any redis instance, tested with the redis docker image

`docker run --rm -p 6379:6379 redis`

set redis hostname, password, tls

`export REDIS_HOSTNAME=localhost:6379`
<br>

`export REDIS_PASSWORD=<password>`
<br>

`export IS_TLS=true`
<br>

then run it:
`cargo run`

if it worked you should see some output, like:
```
******** Running SET, GET, INCR commands ********value for 'foo' = bar
counter = 4

******** Running HASH commands ********
info for rust redis driver: {"name": "redis-rs", "repo": "https://github.com/mitsuhiko/redis-rs", "version": "0.19.0"}
go redis driver repo: "https://github.com/go-redis/redis"

******** Running LIST commands ********
first item: item-1
num of items in list = 4
listing items in list
item: item-2
item: item-3
item: item-2
item: item-3

******** Running SET commands ********
does user1 exist in the set? true
listing users in set
user: user1
user: user2

******** Running SORTED SET commands ********
listing players and scores
player-4 = 1
player-5 = 4
player-3 = 5
player-1 = 8
player-2 = 9
```
