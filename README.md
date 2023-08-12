# trix
trix is a cerealization protocol for [promise pipelining](http://www.erights.org/elib/distrib/pipeline.html) over EVM-based JSON-RPC. 

## Motivation

Fetching hierarchical data is a common challenge in RPC-based systems. The naive solution requires H+1 client-side RPC calls, which degrades performance as your system grows in complexity. In traditional environments, this problem is commonly addressed using [BFFs](https://learn.microsoft.com/en-us/azure/architecture/patterns/backends-for-frontends), [eager loading](https://laraveljsonapi.io/docs/1.0/schemas/eager-loading.html), or with GraphQL. However, applying the BFF pattern at scale on Ethereum is economically infeasible, eager loading is not supported, and although GraphQL-based protocols exist to address this issue, I don't believe that application developers should have to pay for a basic data access right.

This whitepaper, and reference contract, demonstrate how promise pipelining can be achieved in the EVM, and how it can be used in conjunction with `multicall` to simultaneously join several independent models in a single request. My hope is that this contribution makes web3 development, and the client-side runtime performance, suck less. In the future, I hope supporting packages are created to provide either a GraphQL, or a JSON-API [include](https://jsonapi.org/format/#fetching-includes) style interface to facilitate contract interaction.
