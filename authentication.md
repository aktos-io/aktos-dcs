# Authentication

### Login

1. Send `username` + `password` to server. 
2. Check if user exists in the database. 
2. If exists, generate a random token in server 
3. Add the following object to the temporary authentication table:
    ```ls
    {
      token: new-token 
      user: the-user-id 
      authorized: [some, objects] 
      timestamp: some-timestamp
    }
    ``` 
4. Send the token to the client.

### Authenticating messages 

1. Any messages should be dropped if it doesn't exist in the temporary authentication table. 

### Authorization 

1. At the destination, all messages will be checked if sender is authorized to perform that action. 
2. If unauthorized, send an exception message back. 
