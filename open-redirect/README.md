# Open Redirect

> _Open redirect_ occurs when a target visits a website and that website send their browser
> to a different URL, potentially in a separate domain.

`Open Redirects exploit the trust of a given domain to lure targets to a malicious website.`

<details>
    <summary>Occurs when:</summary>
    <p>A developer mistrust attacker controlled input to redirect to anothers site using:</p>
        <ul>
            <li><meta> refresh tags</li>
            <li>DOM window location property</li>
        </ul>
</details>

## Simple exploit examples 

1. URL Parameter
You set a redirect\_to url parameter without validating if you are sendind the user to a legitimate site.
`http://myownsite.com/?redirect_to=attacker_site.com`

2. HTML &lt;meta&gt; tags
This tags can tell browsers to refresh a web page and make a GET request to a URL defined in the tag's content attribute
>&ls;meta http-equiv="refresh" content="0; url="attackaer\_site.com/"&gt;

3. Javascript DOM modification
The DOM is an API for HTML and XML documents that allows developers to modifi the structure, style, 
and content of a web page. Because the __location__ property denotes where a request should be
redirect to the specified URL. 
```javascript
   window.location = attackersite.com
   window.location.href = attackersite.com
   window.location.replace(attackersite.com
```
> Obviously you will need to execute js, either via cross-site scripting or where the site
> allow users to define a URL to redirect to.
