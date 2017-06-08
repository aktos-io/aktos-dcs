# aktos-dcs-design

## Message format:

```
timestamp: unix time (in seconds)
msg_id: sequence number of message (message is identified by timestamp+msg_id)
topic: topic to publish
payload: data to send
```

## Extending Actor

```ls
class MyActor extends Actor
    (init, params) ->
        super 'my actor name'

        @subscribe do
            \some.topic
            \another.topic

        @on-receive (msg) ~>
            # this handler will be run whenever a message is arrived

        @on-kill ~>
            # this handler will be run when actor.kill! is called 

    action: ->
        # this function is called after init part is completed
        @send {some: 'message'}, 'to.a.topic.*'

```

## Actor Methods

actor.kill: Kills the actor. Pass any functions which will be run before kill
    in `@on-kill`
