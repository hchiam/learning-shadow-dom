# Learning Shadow DOM

Just one of the things I'm learning. <https://github.com/hchiam/learning>

<https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM>

```html
<div>
  <p>Hi! Shadow elements encapsulate/insulate inner parts. Think <code>&lt;video&gt;</code> components.</p>
  <div id="shadow-host"></div>
</div>
<script>
  const elementRef = document.getElementById('shadow-host');
  const shadowRoot = elementRef.attachShadow({mode: 'open'});
  const paragraph = document.createElement('p');
  paragraph.innerText = 'Paragraph inside shadow root.';
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
