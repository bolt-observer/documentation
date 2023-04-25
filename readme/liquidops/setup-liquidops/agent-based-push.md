# Agent based - push

Our push based system is based on our open source agent [https://github.com/bolt-observer/agent](https://github.com/bolt-observer/agent)

Agent is a program that essentially interfaces between your node and our platform, gathering data from your node's api and converting it to a compatible format for our platform to ingest it.&#x20;

Interacting with our platform through agent gives you the most control over data, sampling rates and security as we don't need any access to your node, you only ship relevant data to us. You can filter specific channels, add entroy to data you share with us and review the code that is running so you know exactly what its doing.

Agent is considered a reference implementation of how interaction with our platform can be done, API is fairly simple and you can integrate it directly into your tooling if you want to, we do not however at this time provide support for custom integrations (this will change in the future, reach out to us if you'd like to do that at this time).



