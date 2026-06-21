# Architecture

A high-level view of how the home lab is put together.

<pre class="mermaid">
graph TD
    Internet([Internet]) --> Router[Router / Firewall]
    Router --> Switch[Switch]
    Switch --> Server[Lab Server]
    Server --> Containers[Containers]
    Containers --> Web[Web Services]
    Containers --> Monitoring[Monitoring]
    Containers --> Automation[Home Automation]
</pre>

The diagram above is rendered with [Mermaid](https://mermaid.js.org/) loaded from a CDN.
