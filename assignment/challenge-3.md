# gRPC request

## Enable gRPC Support
- Open Bruno and navigate to > Beta and enable support.

1. Open Bruno and create `grpc` request.
2. Enter name `grpc-beta` and URL `grpcs://grpcb.in`
3. Click on method icon and select `SUM` from dropdown
4. Go to `Message` section and click auto fill icon to generate auto message.
5. Execute the request

Compare response with:

Your response contain addition of two values sent in message as `v` 
```js
{
  "v": "addition-of-num",
  "err": ""
}
```

