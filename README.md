# So, what even is this?!

This _should_ be a friendly and safe playground to get an ELK logging stack up and running, and stable of course.

What you'll find in this repo, or .7z file probably, is a number of things:

- ./elasticsearch (contains the necessary configs and volume mount point for... elasticsearch oddly enough)
- ./kibana (contains the necessary configs and volumes mount point for... kibana)
- ./logstash (you get the picture)
- ./docker-compose.yml (the compose file that makes the magic happen)

## Right, that all sounds good... how do I use it?

Yeah I prefer to just get on with it too, so here goes. The process _should_ be simple, but as anyone who's done something like this at least once before - nothing is ever simple, and seldom works first time... so expect... some disruption.

Anyway, to get started, simply run this command:

```
cd <whatever path you've extracted / cloned this stuff into>

docker-compose up --build
    # I'd recommend these other args too
    # --force-recreate (forces a proper recreation of volumes and containers etc)
    # --remove-orphans (stopping and starting this stuff tends to leave behind dangling (hur hur) orphaned containers)
```

And that _should_ be it... if you get anything about a complaint that your machine can't find Docker or docker-compose then you've got bigger problems I'm afraid. Not to worry too much though, Chocolatey - or brew if you used a _proper_ computer instead of those consumer-friendly "Windows" things you've got there, it should be a simple case of ~~`brew install docker`~~ sorry, I meant `choco install docker-for-windows`.

ProTip | when using the obviously superior operating system here - apart for running Docker on I guess... - you'll want to prep your Windows Subsystem for Linux (WSL) by running  `wsl -d docker-desktop sysctl -w vm.max_map_count=262144`.

## It worked first time!!

I bet it didn't, but I'll assume at this point you've got something running. I mean, I just have to, otherwise... otherwise what's the point? What's the point in anything really?! Anyway, I digress - let's take a look at the how and why this is all working.

### **E** - Elasticsearch

This is basically a free and open-source full-text search and analytics engine. Luckily for us, the authors have gone the extra mile to plonk a fancy web front-end over the top of it. That's just what open-source people do, they're amazing and we'd be lost without 'em. Anyway, I digress again, this tool is what essentially parses all of your log files in all of their disparate formats and shapes and sizes and encodings and everything else to produce a nicely consistent set of log information that it can stash in log... stash.

### **L** - Logstash

So these nicely prepared logs that Elasticsearch has just prepared for us - this is where they sit. That's it really, they don't do much here other than get sorted and filtered and aggregated into nice piles and shelves and cupboards and all that sort of stuff, ready for the next bit.

### **K** - Kibana

This is the infamous **next bit** which takes that nicely prepared logging information from the stash and gives those fancy executives in suits and shiny, pointy, really - and I mean really - long shoes (kind of like clown shoes, if clowns were professional) something to point and nod at as though they know what they're looking at, well, they kind of do - because through the power of Kibana you've made complicated data easy enough for anyone, even those idiots, to understand!

Where was I... oh yes, the clown shoes. So this is the tool that presents that logging information into easily digestible information that expensive DevOps people sit around to see when nodes are fuxx0rd or whether they're up and healthy and it can also show things like how many concurrent instances of things there are, how much stuff costs and blah blah blah.
