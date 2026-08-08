# Embedding the call sheet guide in the community

Paste this into a **custom HTML / embed block** on a Mighty Networks page.

If your Netlify address is different, change the URL on the `src=` line — that's the
only thing you ever need to edit.

```html
<div style="max-width:760px;margin:0 auto;">
  <iframe
    id="lesko-callsheet"
    src="https://lesko-callsheet.netlify.app/"
    title="LeskoHelp — your call sheet"
    loading="lazy"
    style="width:100%;height:6800px;border:0;display:block;background:#faf6ec;"
  ></iframe>
</div>

<script>
(function(){
  var f = document.getElementById('lesko-callsheet');
  window.addEventListener('message', function(e){
    if(e.data && e.data.type === 'lesko-callsheet-height' && e.data.height > 400){
      f.style.height = e.data.height + 'px';
    }
  });
})();
</script>
```

## How it works

The page tells the frame how tall it is, so the frame grows and shrinks with the
content — no scrollbar inside a scrollbar. It re-reports after clicks and while a
member is filling in the request builder, since that section changes height as it
fills. If Mighty Networks strips the `<script>` (some plans do), the `height:6800px`
fallback still shows the whole page; it just won't resize. Everything keeps working
either way.

## Simple version

No script, fixed height. Use this if the one above gives you trouble:

```html
<iframe
  src="https://lesko-callsheet.netlify.app/"
  title="LeskoHelp — your call sheet"
  style="width:100%;height:6800px;border:0;display:block;background:#faf6ec;"
></iframe>
```

## Worth knowing

- Nothing a member types into the request builder is saved or sent anywhere — it lives
  in their browser for as long as the page is open, and that's it.
- Once the video is embedded the page gets a little taller — raise `6800px` to about
  `7200px` if you're using the fixed-height version.
- The quick-jump links at the top use `#anchors`. Inside an iframe they scroll within
  the frame, which works fine once the frame is full height.
- Prefer no frame at all? Just link straight to `https://lesko-callsheet.netlify.app/`
  from a button or menu item. It's built to work well on phones on its own.
