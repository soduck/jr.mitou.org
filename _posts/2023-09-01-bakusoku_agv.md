---
layout: post
title: "爆速AGV"
permalink: /projects/2023/bakusoku_agv
thumbnail: /assets/img/thumbnails/2023/bakusoku_agv.webp
description: "高速を発揮し、かつ、小回りのきく独立ステアリング機構を搭載したAGVです。最近、物流2042問題など私たちの生活を支えるロジスティクスが逼迫していますが、このPJで開発しているような高速AGVはロジスティクスの効率向上に寄与できると期待できます。設計にはトポロジー最適化を用いるなどして工夫しています。"
---

{% assign pj = site.data.projects | where_exp: "pj", "pj.id == 'bakusoku_agv'" | first %}

<img class='top-img lazyload' src='/assets/img/spinner.svg' alt='サムネイル画像' loading='lazy'
{% if pj.thumbnail %}    data-src='/assets/img/thumbnails/{{ pj.year }}/{{ pj.thumbnail }}'
{% else %}               data-src='/assets/img/thumbnails/tbu.webp'
{% endif %}                 style='margin-bottom: 10px; border-radius: 6px;' />

{{ pj.description }}

<div class='flex'>
  {% if pj.link %}
    {% if pj.link contains 'github.com' %}
       <a href='{{ pj.link }}' target='_blank' class='button'>ソースコードを見る</a>
    {% else %}
       <a href='{{ pj.link }}' target='_blank' class='button'>公式サイトを見る</a>
    {% endif %}
  {% endif %}

  <a href="https://twitter.com/intent/tweet?text={{ pj.title }}&via=MitouJr&hashtags=未踏ジュニア{% if pj.tags %},{{ pj.tags | join: ','}}{% endif %}&related=MitouJr&lang=jp&url={{ site.url }}/projects/{{ pj.year }}/{{ pj.id }}" class="button" target="_blank" rel="noopener">ツイートする</a>
</div>

### クリエータ {#creator}
<p>
  {% for creator_id in pj.creator_ids %}
    {% include creator.html is_simple=true %}
  {% endfor %}
  <small>(<a href='/projects/{{ pj.year }}'>{{ pj.year }}年度</a> 採択 / {% include link-to-mentor.html id=pj.mentor_id %}PM)</small>
</p>

{% if pj.comment %}
### PMコメント {#comment}
<p class="project-comment">{{ pj.comment }}</p>
{% endif %}

{% if pj.promotion %}
{% if pj.promotion contains '.gif' %}
## デモ動画 {#demo}
<img class='top-img lazyload' src='/assets/img/spinner.svg' alt='デモ動画 (Gif)'
     data-src='/assets/img/thumbnails/{{ pj.year }}/{{ pj.promotion }}' loading='lazy'
     style='margin-bottom: 10px; border-radius: 6px;' />
{% else %}
## デモ動画 {#demo}
<div class="youtube">
  <iframe width="560" height="315" class="lazyload" data-src="https://www.youtube.com/embed/{{ pj.promotion }}?rel=0" frameborder="0" allowfullscreen=""></iframe>
</div>
<a href="https://youtu.be/{{ pj.promotion }}" target="_blank" rel="noopener" class="button">YouTube で見る</a>
{% endif %}
{% endif %}

{% if pj.final %}
## 発表動画 {#final}
<div class="youtube">
  <iframe width="560" height="315" class="lazyload" data-src="https://www.youtube.com/embed/{{ pj.final }}?rel=0{% if pj.final_start %}&start={{ pj.final_start }}{% endif %}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>
</div>
<a href="https://youtu.be/{{ pj.final }}{% if pj.final_start %}?t={{ pj.final_start }}{% endif %}" target="_blank" rel="noopener" class="button">YouTube で見る</a>
{% endif %}

<style type="text/css">
  .prev { display: table-cell; color: white; text-align: left;   }
  .toc  { display: table-cell; color: white; text-align: center; }
  .next { display: table-cell; color: white; text-align: right;  }
  .nav a:link, .nav a:visited { color: white; }
</style>
<div style="display: table; border-collapse: separate; border-spacing: 15px 0; font-size: 70%; width: 100%; padding: 10px 10px; margin-top: 100px; background-color: rgb(40, 161, 58);">
  <p class="nav prev"><a href='motion_simulator'>&larr; 前<br>
    Motion Simulator - 動き、風が吹き、水が出...</a></p>
  <p class="nav next"><a href='ai_4koma_maker'>次 &rarr;<br>
    AI 4コマメーカー</a></p>
</div>

{% include project-navigation.html %}