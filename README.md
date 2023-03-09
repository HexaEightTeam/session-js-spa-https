# Hexaight Session For Single Page Apps and Websites using JavaScript

## Implement HexaEight Authentication in Javascript using the following steps

1. Add the below script tag to the HEAD section

```
      <script src="https://cdn.jsdelivr.net/gh/hexaeightteam/session-js-spa-https/hexaeightsession.js"></script>
      <script src="https://cdn.jsdelivr.net/npm/axios@1.1.2/dist/axios.min.js"></script>
      <script src="https://cdn.jsdelivr.net/gh/hexaeightteam/session-js-spa-https/hexaeightaxios.js"></script>
```
(NPM version will be released soon...)

2. Add the below script to the page. We need to add JQuery cdn since we are using $ below.


```
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>


<script>
  const session = new HexaEight();
  $(document).ready(async function() {
	const clientid  = "87ADEE......";
	const tokenserverurl =  "https://mytokenserver:5000";
	const state = await session.init(clientid,tokenserverurl);
 
    // Prevent page reload on refresh
    window.addEventListener("beforeunload", function(e) {
      e.preventDefault();
      e.returnValue = "";
    });
  }); 
</script>
```

Client ID can be obtained from Token server.  If you have not enabled https on token server, use session-js-spa-http repository for reference

Sample Demos integrated using External Builder and/or Hosted on external sites.

[Sessions Demo on nicepage.io](https://hexaeight-session.nicepage.io/) - Site was built using NicePage Free desktop tool and published to their site. (Post authentication capabilities will be added to site shortly for demo purposes) 

More site will be added shortly to show case the capability of authenticating multiple external sites using a single self hosted token server

**Limitation : This authentication works only for Single Page Applications.**  

**There is also a http authentication library in case you want to use HexaEight session over HTTP. (Will be available shortly)**

**HexaEight Session implements application layer enncryption using authenticated encryption and hence does NOT depend on HTTPS for functionality**


