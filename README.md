# eval.liquid

Evaluate Liquid `{% link ... %}` tags stored in plaintext.

See [kevinlin1/just-the-class](https://github.com/kevinlin1/just-the-class) for a real-world use case.

## Usage

Download the [`_includes`](/_includes) into your Jekyll website's `_includes` folder. Then, follow the usage instructions in the `eval.liquid` file.

- In a **markdown file**, call `eval.liquid` using the `include` tag, where `site.data.example.link` is substituted with your string content.

  ```
  {% include eval.liquid content=site.data.example.link %}
  ```

- In a **layout (or HTML) file**, call `eval.liquid` using the `include` tag, capture the result, and then markdownify it so that the links are rendered properly.

  ```
  {% capture example %}{% include eval.liquid content=site.data.example.link %}{% endcapture %}
  {{ example | markdownify }}
  ```
