---
title: "[github] 페이지 사이즈 커스텀"
excerpt: "페이지 사이즈 커스텀 하는 방법! "

categories:
- github 
  tags:
- [content]
  
  toc: true
  toc_sticky: true
  
last_modified_at: 2021-11-11T18:00:00-05:00
---

This post should not appear in the search index because it has the following YAML Front Matter:

```yaml
search: false
```

**Note:** `search: false` only works to exclude posts when using Lunr as a search provider.
{: .notice--info}

To exclude files when using Algolia as a search provider add an array to `algolia.files_to_exclude` in your `_config.yml`. For more configuration options be sure to check their [full documentation](https://community.algolia.com/jekyll-algolia/options.html).

```yaml
algolia:
  # Exclude more files from indexing
  files_to_exclude:
    - index.html
    - index.md
    - excluded-file.html
    - _posts/2017-11-28-post-exclude-search.md
    - subdirectory/*.html
```