---
title: "100 Days of Code: Day 1"
date: "2022-07-31T10:00:00.000Z"
template: "post"
draft: false
category: "100 Days of Code"
tags:
  - "100 Days of Code"
  - "C#"
  - "Azure Functions"
description: "Day 1 of 100 Days of Code: Using Azure Functions, Shopify Multipass, and Sign In with Apple. Getting Started."
socialImage: "/media/default-social-image.jpg"
---


# 100 Days of Code: Day 1
In studying for my AZ-204, I needed to get moving on a project. This is a test that I've been delaying for about two years now, and it's time I get on it.

My first project is working on an Azure Function to generate tokens for Shopify's [Multipass](https://shopify.dev/api/multipass) feature. Multipass is a feature that allows you to generate a unique token that authenticates a new or existing customer account into a Shopify store.

Generating the token doesn't require anything special, except for a customer JSON object that will be used to create a customer with an account on the store. To use it properly however, it's best utilized with an external [IDP](https://en.wikipedia.org/wiki/Identity_provider), such as [Sign In with Apple](https://developer.apple.com/sign-in-with-apple/).

Here is a high level overview of how I imagine this will work - TBD.

```plantuml
@startuml
:Sign In with Apple ID (Shopify Storefront);

if (Authentication Success) then (Yes)
  :Redirect to Azure Function;
  :Generate Multipass Token;
  :Redirect to Multipass Endpoint;

  if (Multipass Validated) then (Yes)
    :Login or Create/Login Customer;
  else (No)
    :Error;
  endif

else (No)
  :Redirect to Failure Page;
endif

stop

@enduml
```

Time to get started, will get some source code posted as soon as it's fit for testing.