# js-session-spa

## Implement HexaEight Authentication in Javascript using the following steps

1. Add the below script tag to the HEAD section

```
<script src="./hexaeightsession.js">
<script src="./hexaeightaxios.js">
```
2. Add the below script to the page.

```
<script>
  const session = new HexaEight();
  $(document).ready(async function() {
	const clientid  = "87ADEE......";
	const tokenserverurl =  "http://mytokenserver:5000";
	const state = await session.init(clientid,tokenserverurl);
 
    // Prevent page reload on refresh
    window.addEventListener("beforeunload", function(e) {
      e.preventDefault();
      e.returnValue = "";
    });
  }); 
</script>
```

!!! Limitation : This authentication works only for Single Page Applications. 
