# Get Started

Welcome to Mercury's documentation for developers. This rust book is meant to give you a complete understanding of
Mercury's features and what you need in getting started using Mercury's preview releases as the indexer for your
services, apps, and protocols; so if some points need clarification don't hesitate to let us know by opening an issue
on Github.

<br/>

# Mercury: a Managed Indexing Service

Let's start off by saying that Mercury is a managed indexing service, which means that we control on our servers
everything ranging from ingestion to the GraphQL API. 

This design choice is likely what will impact more your decision in choosing an indexer, here are some of the
pros and cons of using a managed indexer service.

> Note: these charateristics aren't about Mercury specifically, they are about the advantages and disadvantages
> of relying on a managed indexing service.

#### Pros of a managed service.
- No need for a setup and development of any kind.
  * this also includes not needing to worry about DB structure and its efficiency
  
- No need of performing maintenance. There is no workload that is streamlined to the user, so also no workload
in having to stay up to date with the code, dependencies, etc.

- Cheaper. In most circumnstances, using a managed indexer is cheaper than running and maintaining your own instance.
Also, you might want to account for development costs, which are non-existing when relying on a managed service.

- Security. While it's true that you don't have control over the security of the product you're relying to,
our team does. We are committed to building a secure product and also have a solid background in security research.

- Smoother experience. Generally, managed services can offer a smoother experience due to the nature of their design,
including also more specific support.

#### Pros of a self-hosted service.
- Vendor lock-in. When you're running your own indexer you don't have much constraints around which server you use and
you don't have to worry about lack of availability on the service's end. For example, if you want to migrate to another
service, self-hosted services offer a much smoother experience, and in some managed service that is not even an option.

- Customization. As you're actually building the service yourself, you can give it the shape you want. In some situations
where very high customization degrees are needed, relying on a self-hosted service reduces a lot of workload for the
client.

<br/>

You can understand that the choicce depends on you use case and needs. If you'd like to get help in understanding if
Mercury fits your requirements you can ask on our team's public discord server.

Anyways, for Mercury we are committed to lowering the gaps between a self-hosted solution's pros and a managed's cons. 
In fact:
- we tackle customizability by developing and integrating in Mercury the Zephyr VM, xyclooLab's WebAssembly VM for 
communication between the Stellar Network's data and the guest environemnt. Users that wish to have full customizability
(and also additional perks) can write their logic in any WASM-compatible language and deploy it to Mercury's cloud
execution environment. Read more about Zephyr in our blog [here - introduction](https://blog.xycloo.com/blog/introducing-zephyr) 
and [here - an experimental Zephyr program](https://blog.xycloo.com/blog/zephyr-pre-alpha-preview).
	* also, we generally don't envision Mercury itself not to cover most use cases, even those who need some customizability.
	Our extensive knowledge of Stellar + Soroban structures, dynamics, and logics are helping us to craft an implementation
	that will fit most use cases for developers. This is also why we have developed the Zephyr Virtual Machine with also other features
	in mind.

- there isn't really a way of tackling vendor lock and ensuring availability over time, but:
  * we're committed with working with users that wish to migrate in order to provide
  the cleanest migration experience as possible. In our mind we have DB write channels, but
  this is not going to be prioritized and included in the first releases. 
  * while it is not possible for us to, at least currently, guarantee consistent availability over time, our team is committed
  to do so. We have been working on Stellar for more than two years and have strong ties with the community, of which we
  are also a part.

<br/>

## Pricing

While we don't have yet any hard numbers on pricing, we have defined a very solid model that involves
down-payments and reimbursements. The main advantages of our cost model are:

- very cost efficient: you only pay for the data you request to store, and for the amount
of data you're actually occupying in our database. 
- efficiency in managing payments: you know exactly how much you'll spend at most.
- payments are performed through stellar payments.

If you're interested in learning more, we suggest checking out our [SCF presentation document](https://docs.google.com/document/d/16rgq5mopskhU4CFE69VAi--IsCxNDeNjBlb-buidl08).
