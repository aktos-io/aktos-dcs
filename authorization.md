One or more roles can be assigned to a user, like so:  

```ls
user-db =
    * _id: 'user1'
      passwd-hash: "0u1Dsf0uVy"
      roles:
          'test-area-reader'

    * _id: 'user2'
      passwd-hash: "CG8oxxJmXE"
      roles:
          \test-area-writer

    * _id: 'user3'
      passwd-hash: "81fb2Rij9C"
      roles:
          \my-test-role2
```

Permissions are defined by assigning one or more `rw`, `ro` values and/or by inheritance: 

```ls 
permission-db =
    * _id: \test-area-reader
      ro: \authorization.test1

    * _id: \test-area-writer
      inherits:
          \test-area-reader
      rw:
          \authorization.test1

    * _id: \my-test-role
      ro:
          'my-test-topic1'
          'my-test-topic2'
      rw:
          'my-test-topic-rw3'

    * _id: \my-test-role2
      inherits:
          \my-test-role
          \test-area-writer
      rw:
          'my-test-topicrw4'
          
```

For example, permissions for `user3` are calculated as follows:
  
```ls
'some-random-token-generated-for-user3':
    rw:
        'my-test-topic-rw3'
        'authorization.test1'
        'my-test-topicrw4'
    ro:
        'my-test-topic1'
        'my-test-topic2'
        'authorization.test1'     
```
