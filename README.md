# activitypub.rocks

This is the repo for maintaining https://activitypub.rocks/

## Building the site

The site uses a static site generator called [Haunt](https://dthompson.us/projects/haunt.html) to generate HTML from Scheme .scm files.

To make it easier to work with for those who are not familiar with Scheme, there is a Docker image that can be used to build the site. From your working directory, run:

```bash
docker run --rm -it -v"$(pwd)":/src -w /src ghcr.io/evanp/haunt:latest /usr/bin/haunt build
```

This will generate the site in the `site` subdirectory of your working directory. The output is ignored by Git, and just used for testing your changes to the Scheme files.

The current code uses absolute paths for links and images, so your site will not look great when loaded from the filesystem directly. You can use a local web server to serve the site, again using Docker from the same working directory:

```bash
docker run --rm -it -v "$(pwd)/site":/usr/share/nginx/html:ro -p 8080:80 nginx:alpine
```

This will start a web server on port 8080, and you can view the site at `http://localhost:8080/`. You can also use any other web server you prefer, such as Python's built-in HTTP server or Node.js's http-server.

## Editorial process

## Design principles

## Topics for coverage

* Primarily ActivityPub and related specifications as a developer stack
* NOT Fediverse culture (e.g. why and how to add alt text)
* NOT existing software implementation details (e.g. a Mastodon administrator's guide)

## Audiences

These are the audiences in sequence of priority and questions they might want to ask.

1. Developers
   * "I just heard about this thing called ActivityPub, and I need to wrap my mind around what it is in a short amount of time."
   * "I need to find developer tools that can help me implement ActivityPub in my applications."
   * "I need to understand the **ActivityPub stack**, including HTTP Signature, Webfinger, Activity Streams 2.0, and other relevant standards and technologies."
   * "I have questions or need guidance. What resources are there for me to get help with my AP stack development?"
   * "What are the relevant standards documents for AP stack development?"
   * "What are the standards development processes and groups? What is a FEP?"
   * "What work is being done right now in extending the standard, including the FEP process and SocialCG task forces?"
   * "How do I convince my boss that we need to include ActivityPub in our product?"
2. Press and journalists
   * "What are some existing press kits for the ActivityPub stack?"
   * "What is this technology for? Who benefits?"
   * "How big is it? How important is it? Why does it matter to my readers?"
3. Decision makers and policy makers
   * "Why should my organisation use ActivityPub?"
   * "How does ActivityPub interact with privacy requirements?"
   * "Is it safe for citizens to use?"
   * "What is its effect on competition in a market?"
   * "What are some case studies of success with ActivityPub?"
4. End users
    * "How do I get started using ActivityPub-enabled software or services?"
    * "Where are there other resources for end-users to learn about the Fediverse and ActivityPub?"
