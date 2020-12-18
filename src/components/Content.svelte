<script>
    let html_content = "<strong>Hello</strong>, <em>Sparky</em>";
</script>

<div>Escaped html: {html_content}</div>
vs
<div>
    unescaped:
    {@html html_content}
</div>
