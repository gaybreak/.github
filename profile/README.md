# daybreak (WIP)

<!-- add crates.io, docs.rs and discord server invite buttons here -->

## whats this?

a framework for (mainly) discord bots that includes most stuff you'd need and
does a lot for you, so you can focus on actual code and not boilerplate

## how's this more convenient

we'll insert a code example here when we actually code it

## why this and not [serenity](https://github.com/serenity-rs/serenity) or [twilight](https://github.com/twilight-rs/twilight)

both are great libraries, they just have different opinions than us, see below
for what makes this different

## performance is overrated

your code's overhead will be like 1-5% of the overhead of network *(unless you're
doing fancy stuff like image processing)*, this means we can be spoiled and put
convenience over performance, how long it takes to code the thing matters too

### caching on disk? really??

we know this is unorthodox but bare with us, cause we have our reasons:

#### no more ram bottleneck

in the real-world, your only bottleneck will be the ram usage, and ram is
expensive, but do you really need it to be on ram? the io overhead won't matter
and you probably already need a persistent database for guild configs and all

#### you can just cache everything

twilight has ways to filter what to cache, you can take it further by caching
everything yourself but those are hard to get right, to the point where 90% of
errors are cache-related

#### basically all the benefits of redis

the database is another process, meaning you can:

1. not worry about deadlocking
2. fearlessly restart your bot
3. count on data-safety guarantees of the database backend
4. interop the program easily
5. use backend's powerful statistics/analyzes easily
6. encrypt everything by default, being ready to be verified by discord
7. manually query the database and check it out at runtime
8. and more

#### but why force postgresql?

because its the most loved and for good reason, it works for everything
meaning we won't need separate processes for your custom database and the cache,
we tried a proof-of-concept for mongodb and realized this is not one of its use-cases

## repo/org/team stuff

### who are you anyway?

it's just [mars](https://github.com/bulletsabbath) and [lara](https://github.com/laralove143)
for now, that may or may not change in the future

### how can i help

you can create issues for feature-requests and bugs or contribute, please do actually!

### why the name daybreak

this is the opposite of [twilight](https://github.com/twilight-rs/twilight) in a
lot of ways, so we thought the name should be the oppoiste of it too

we thought about a lot of other stuff like discrust but they were all taken :(

### why's the organization name gaybreak and not daybreak

daybreak was taken, we could do daybreak-rs yeah but gaybreak was too tempting..
