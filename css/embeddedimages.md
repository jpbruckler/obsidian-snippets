
source: discord
user: Anubis#5850
discordId: 928339066838216754

This is the css that applies to every image that you embed in the note:
(Obv. you have to specify the max-width values yourself, what i use is 50% and 90%)

```css
.markdown-preview-view .internal-embed img {
    display: block;
    max-width: 50%;
    opacity: 0.7;
    transition: max-width 0.25s 0.25s, transform 0s, opacity 0.25s 0.25s;
}

.markdown-preview-view .internal-embed img:hover {
    cursor: zoom-in;
    max-width: 90%;
    opacity: 1;
}
```

If you want certain css classes to be excluded, you can append :not(.customClass) to .markdown-preview-view (I have .homepage disabled which is my dashboard)
And here's some extra css i use for my images to make them look a bit better (Rounded borders and centered images 😄):

```css
.markdown-preview-view .internal-embed img {
    border-radius: 10px;
    margin-left: auto;
    margin-right: auto;
}
```