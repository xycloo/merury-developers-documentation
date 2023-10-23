# Subscriptions: What and Why

As you've read in the introduction, Mercury only stores the data you request. This translates to us adopting
our so-called "subscriptions-based" model.

The "subscriptions-based" model consists in users having to create subscriptions through our
subscriptions backend. 

> Note: When Mercury will release its first stable release, payments to Mercury
> will begin when creating the subscription.

A user subscription defines the charateristics that the Network data ingested by Mercury's ingestor
must have in order to be stored on our database (thus subsequently queried). 

## Example

Imagine having a factory contract. You'd want to be able to keep track of the contracts
deployed by your factory, and your factory contract emits a contract event `(Symbol("deploy"), created_by, deployed_id)`
whenever it deployed a new contract.

If you go for an event-based approach, you can set up a subscription to all contract events for all your
factory's `"deploy"` events:

Subscription:

```json
{
	"contract_id" : "contract id (as strkey)",
	"max_single_size": 144,
	"topic1": "'deploy' as base64 xdr"
}
```

> `max_single_size` is the maximum amount of bytes a single event can reach.

## About subscription customizability

Subscruptions offer a good level of customizability in the data you want to be able to query. Say for example
in the example above you only want to store `deploy` events where `created_by` is a specific address, you 
can easily achive this by making the subscription look like:

```json
{
	"contract_id" : "contract id (as strkey)",
	"max_single_size": 144,
	"topic1": "'deploy' as base64 xdr",
	"topic2": "specific address as base64 xdr",
}
```

You could also subscribe to all the contract's event with

```json
{
	"contract_id" : "contract id (as strkey)",
	"max_single_size": 144,
}
```

<br/>

In the next sections of the documentation, we'll guide you through how to create subscriptions to the currently indexed
data structures.
