# Repro for `IBMa/equal-access` issue [`#1892`](https://github.com/IBMa/equal-access/issues/1892)

Steps:
- open 2 terminal windows
  - in the first run `npm run server`
  - in the second run `npm run test`
- wait until the test is finished or you see `Navigation timeout of 30000 ms exceeded`

Run `npm run test-ok` to verify that the test can pass when a lazily loaded iframe is visible.

The only difference is that the broken test has : 

```html
<div style="display: none;">
	<iframe loading="lazy" src="https://example.com/" frameborder="0"></iframe>
</div>
```

While the ok test other as :

```html
<div>
	<iframe loading="lazy" src="https://example.com/" frameborder="0"></iframe>
</div>
```
