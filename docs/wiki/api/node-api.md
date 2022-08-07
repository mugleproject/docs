# Node API

The API is used to query a node about various information on the blockchain, networks and peers. By default, the API will listen on `localhost:6813`. The API is started at the same time as the mugle node.
This endpoint requires, by default, [basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). The username is `mugle`.

## Node API v2

This API version uses JSON-RPC for its requests. It is split up into a foreign API and an owner API. The documentation for these endpoints is automatically generated:

* [Owner API](https://docs.rs/mugle_api/latest/mugle_api/trait.OwnerRpc.html)
* [Foreign API](https://docs.rs/mugle_api/latest/mugle_api/trait.ForeignRpc.html)

Basic auth passwords can be found in `.api_secret`/`.foreign_api_secret` files respectively.

!!! note "Postman"
    A complete Postman collection for the Mugle Node API can be found [here](https://forum.mugle.org/t/full-postman-collection-for-mugle-node-api/7696).

## Node API v1

**Note:** version 1 of the API will be deprecated in v4.0.0 and subsequently removed in v5.0.0. Users of this API are encouraged to upgrade to API v2.

This API uses REST for its requests. To learn about what specific calls can be made read the [node API v1 doc](https://github.com/mugleproject/mugle/blob/master/doc/api/node_api_v1.md).

Basic auth password can be found in `.api_secret`
