# valtio-umd-cdn

Demo: [https://ab498.github.io/cdn/example.html](https://ab498.github.io/cdn/example.html)
<br>
CDN: `<script src="https://ab498.github.io/cdn/valtio-standalone.js"></script>`
<br>

```html
<div id="root"></div>
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<script src="https://ab498.github.io/cdn/valtio-standalone.js"></script>
<script type="text/babel">
    const state = Valtio.proxy({ count: 0, text: 'hello' })
    // This will re-render on `state.count` change but not on `state.text` change
    function Counter() {
        const snap = Valtio.useSnapshot(state)
        return (
            <div>
                {snap.count}
                <button onClick={() => ++state.count}>+1 Count</button>
                <button onClick={() => state.text = state.text == 'hello' ? 'world' : 'hello'}>Alter Text</button>
            </div>
        )
    }
    ReactDOM.createRoot(document.getElementById('root')).render(<Counter />)
</script>
```

```bash
> Object.keys(window.Valtio)

[
    "deepClone",
    "devtools",
    "getVersion",
    "proxy",
    "proxyMap",
    "proxySet",
    "ref",
    "snapshot",
    "subscribe",
    "subscribeKey",
    "unstable_getInternalStates",
    "unstable_replaceInternalFunction",
    "useProxy",
    "useSnapshot",
    "watch"
]
```
