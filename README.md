# techpants.io

Static landing page that curates top tech pants and provides simple filtering so visitors can compare fabrics, fits, and use cases quickly.

## Project structure

- `index.html` – main single-page site with layout, styles, and JavaScript that renders the comparison table.
- `techpants.yml` – source of truth for the tech pants list. Each item includes display text, links, pricing, and tags used for filtering.

## Contributing updates

1. Fork or clone the repository.
2. Update `techpants.yml`:
   - Keep the file sorted however you prefer; alphabetical by brand works well.
   - `price` is the human-friendly string (e.g., `"~$79.00"`); `price_numeric` is used for filtering, so provide a numeric value (no currency symbol).
   - `tags` drive the filter dropdown; use lowercase keywords like `office`, `travel`, `outdoor`, `athletic`, or add new ones as needed.
3. Preview the page locally by serving the folder with a static server (for example `python -m http.server`) and visiting `http://localhost:8000/index.html`. Browsers block `fetch` from the local filesystem, so a simple HTTP server keeps the YAML loader happy.
4. Submit a pull request describing the change and why the product should be featured.

## YAML item reference

```yaml
- brand: Example Brand
  model: Product Name
  price: "~$123.45"        # Display text shown in the table
  price_numeric: 123.45    # Number used for filter logic
  link: https://example.com/product
  link_text: Shop Example  # Anchor text for the buy link
  tags:
    - office
    - travel
```

Thanks for helping people discover better, more comfortable pants!
