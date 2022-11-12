# donjekyl -- Using Mastodon for comments on a Jekyll blog

After moving my blog to personal server using Jekyll, I was left with a small problem: how to enable comments?
I certainly don't want to be creating accounts on my server, yet I know that without some form of control
blog comments can rapidly fill up with spam. So I set up to enable pair the blog with Mastodon and the
Fediverse as follow:

1. Post a new blog with Jekyll
2. Post an announcement of the blog entry as a Toot
3. Link the blog entry to the announcement
4. Validate the `REPLY` button on the blog entry so it post comments on the Fediverse as replies to the announcement toot
5. Display the responses to the announcement toot as replies

There are existing solutions to the issues 2, 3 and 4, but they require manually posting the announcement Toot,
retrieving its identifier and then manually copying it in the header of the blog page. The first task of `donjekyl`
is to automate these steps.

There are also solutions to the issue 5, but they require running a javascript process on the client when reading the
page. I don't like that too much, because Jekyll normally produces static web sites that do not require any
javascript -- all required processing is done as part of the publishing process. The solution envisaged here
is to download the responses to the announcement toot, and populate a comments page for each blog entry. This
could be managed by `donjekyl`.
