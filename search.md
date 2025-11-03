---
description: ASNA Encore RPG documentation search results
noratings: true
notoc: true
notags: true
title: "Docs search"
skip_read_time: true
---

<div class="container">
  <div id="pagefind-search" class="asna-search asna-search-hero"></div>
</div>

<script defer>
  window.addEventListener('DOMContentLoaded', function () {
    if (window.PagefindUI) {
      const ui = new PagefindUI({
        element: '#pagefind-search',
        translations: { placeholder: 'Search the docs' },
        showSubResults: false,
        showImages: false,
        resetStyles: false
      });
      document.documentElement.style.setProperty('--pagefind-ui-scale','1');

      const q = new URLSearchParams(location.search).get('q');
      if (q) {
        const input = document.querySelector('#pagefind-search input[type="text"]');
        if (input) {
          input.value = q;
          input.dispatchEvent(new Event('input', { bubbles: true }));
        }
      }
    }
  });
</script>
