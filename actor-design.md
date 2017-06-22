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
