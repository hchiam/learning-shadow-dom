# Learning Shadow DOM

Just one of the things I'm learning. <https://github.com/hchiam/learning>

Shadow DOM [enables scoped elements and scoped CSS](https://medium.com/duomly-blockchain-online-courses/shadow-dom-vs-virtual-dom-what-is-the-difference-f2611da536ab). It's used by [Web Components](https://github.com/hchiam/learning-web-components).

Shadow DOM [isolates DOM and scopes CSS](https://web.dev/shadowdom-v1/).

For security/other reasons, [you can't attach shadow DOM to some elements](<https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow#:~:text=there%20are%20some%20that%20can't%20have%20a%20shadow%20dom%20for%20security%20reasons%20(for%20example%20%3Ca%3E).>).

Follow links on this page to learn more: <https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM>

```html
<div>
  <p>
    Hi! Shadow elements encapsulate/insulate inner parts. Think
    <code>&lt;video&gt;</code> components.
  </p>
  <div id="shadow-host"></div>
  <p>
    The styles in the shadow DOM don't leak out so this paragraph doesn't get
    affected
  </p>
</div>
<script>
  const elementRef = document.getElementById("shadow-host");
  const shadowRoot = elementRef.attachShadow({ mode: "open" });
  const paragraph = document.createElement("p");
  paragraph.innerText = "Paragraph inside shadow root.";
  shadowRoot.innerHTML = `<style>p{background:navy;}</style>`;
  shadowRoot.appendChild(paragraph);
</script>
<style>
  body {
    background: #333;
    color: snow;
    font-family: avenir, arial, monospace;
  }
</style>
```
