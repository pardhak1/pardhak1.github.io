---
layout: page
title: Coverage
permalink: /coverage.html
---

Quarterly earnings reports on four tickers — CMG, QSR, MCD, YUM. Each post goes up after that company actually reports (so ~4x/year per ticker, clustered around earnings season). For general industry news between reports, see [Weekly Notes](/weekly.html).

<!-- Live price widget — TradingView, free, no API key needed, updates in the visitor's browser -->
<div class="tradingview-widget-container">
  <div class="tradingview-widget-container__widget"></div>
  <script type="text/javascript" src="https://s3.tradingview.com/external-embedding/embed-widget-symbol-overview.js" async>
  {
  "symbols": [
    ["Chipotle", "NYSE:CMG|1D"],
    ["Restaurant Brands Intl", "NYSE:QSR|1D"],
    ["McDonald's", "NYSE:MCD|1D"],
    ["Yum! Brands", "NYSE:YUM|1D"]
  ],
  "chartOnly": false,
  "width": "100%",
  "height": "400",
  "locale": "en",
  "colorTheme": "light",
  "autosize": true,
  "showVolume": false,
  "showMA": false
  }
  </script>
</div>

{% for ticker in site.tickers %}
### {{ ticker }}
<ul>
  {% assign ticker_posts = site.posts | where_exp: "post", "post.categories contains ticker" %}
  {% for post in ticker_posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> — {{ post.date | date: "%b %-d, %Y" }}
    </li>
  {% endfor %}
  {% if ticker_posts.size == 0 %}
    <li><em>No posts yet.</em></li>
  {% endif %}
</ul>
{% endfor %}
