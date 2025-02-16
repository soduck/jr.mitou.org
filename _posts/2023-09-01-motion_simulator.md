---
layout: post
title: "Motion Simulator - 動き、風が吹き、水が出て、 VRで360度見渡せる椅子に座って仮想現実やゲーム世界での体験をより臨場感のあるものにするデバイス"
permalink: /projects/2023/motion_simulator
thumbnail: /assets/img/thumbnails/2023/motion_simulator.webp
description: "Motion SimulatorはユーザーがVRゴーグルをつけて6自由度の座面に座ると、座面がコンテンツに合わせて動き、風や水が噴射される家庭用デバイスです。映画やVRゲーム、シミュレーションゲームなどでの臨場感を高めることが出来ます。今までは映画館やテーマパークでしか体験できなかったことも家庭で簡単に体験出来るようになります。"
---

{% assign pj = site.data.projects | where_exp: "pj", "pj.id == 'motion_simulator'" | first %}

<div style='margin-top: 50px; margin-bottom: 30px;'>
  <img class='top-img lazyload' src='/assets/img/spinner.svg' alt='サムネイル画像 - {{ pj.title }}'
  {% if pj.thumbnail %}    data-src='/assets/img/thumbnails/{{ pj.year }}/{{ pj.thumbnail }}'
  {% else %}               data-src='/assets/img/thumbnails/tbu.webp'
  {% endif %}                 title='{{ pj.title }}' style='border-radius: 6px;' loading='lazy' />
</div>

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

<nav>
  <p class='nav prev'><a href='hato' title='Hopefully Automatic Train Operation: 没入感を高める!? Nゲージ列車 全自動走行システム'>&larr; 前<br>
    Hopefully Automatic Train Oper...</a></p>
  <p class='nav next'><a href='bakusoku_agv' title='新型独立ステアリング機構の開発およびそれを用いたAGVモジュールの開発'>次 &rarr;<br>
    新型独立ステアリング機構の開発およびそれを用いたAGVモジュ...</a></p>
</nav>

{% include project-navigation.html %}
