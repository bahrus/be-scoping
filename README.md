# be-scoping [TODO]


## Example 1

```html
<div itemscope itemtype="https://schema.org/Movie">
    <h1 itemprop="name">Avatar</h1>
    <span>Director: <span itemprop="director">James Cameron</span> (born August 16,
        1954)</span>
    <span itemprop="genre">Science fiction</span>
    <a href="https://youtu.be/0AY1XIkX7bY" itemprop="trailer">Trailer</a>
    <a itemprop="reviews">See reviews</a>
</div>
<script nomodule be-scoping='{
    "args": ["name"],
    "transform": {
        "reviewsI": "reviews"
    }
}'>
    {
        reviews: `https://www.rottentomatoes.com/search?search=${name}`
    }
</script>
<script nomodule be-let=itempropAs>
    scope[value] = ('href' in target) ? target.href : target.textContent
</script>
```

[TODO]:  Figure out, then explain precisely how be-scoping differs from be-calculating.