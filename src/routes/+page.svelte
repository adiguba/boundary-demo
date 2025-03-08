<p>
    Navigate between the page.
</p>
<ul>
    <li>
        "onerror" contains a svelte:boundary with a bad component that throw an error.<br/>
        The <code>onload</code> handler will show a message and a button to retry, which displays the component correctly.
    </li>
    <li>
        "failed" contains a svelte:boundary with a bad component that throw an error.<br/>
        The <code>failed</code> snippet will show a message and a button to retry, which displays the component correctly.
    </li>
    <li>
        "client" contains a svelte:boundary with a component that only throw an error on server-side.<br/>
        All is fine on client-side.
    </li>
</ul>

<p>➡️ Move between the page on client-side, and all will work as espected.</p>


<p>
    Now, reload the page outside home, and you got an HTTP 500 without content (out of the layout).
</p>