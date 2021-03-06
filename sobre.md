---
layout: page
permalink: /sobre/index.html
title: Sobre
tags:
  - Sobre
  - Papo de Cloud
  - Institucional
chart: true
published: true
---

<!-- <figure>
  <img src="{{ site.url }}/images/logo.png" alt="Papo de Cloud">
</figure> -->

{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}


O **Papo de Cloud** foi criado por Bruno Emer no ano de 2016, e tem como objetivo publicar conteúdo sobre computação em nuvem em português, afim de difundir a utilização de tecnologias escaláveis, econômicas, seguras e principalmente acessíveis.

A idéia de criar um blog com esta temática, surgiu em meados de 2015, quando Bruno se deparou com a dificuldade em encontrar material sobre novas tecnologias, ferramentas e melhores práticas para o provisionamento e manutenção de componentes em ambientes de nuvem em nosso idioma. A partir daí, Bruno convidou alguns de seus amigos e colegas de trabalho e estudo para juntarem-se ao projeto e dar início ao processo de criação dos conteúdos a serem apresentados, entre eles, Gilmar Machado, que participou do projeto desde sua concepção.

O objetivo principal Papo de Cloud é apresentar artigos, tutoriais e compartilhar experiências (boas e ruins) tanto nossas quanto de outros amigos que atuam diariamente na área de TI com todos os interessados no assunto, sejam estudantes, analistas, engenheiros, gerentes, diretores ou apenas curiosos!

Se você já trabalha na área de TI e quer aprender mais sobre computação em nuvem, este blog é pra você. Se você quer trabalhar com TI e tem interesse por arquiteturas escaláveis, plataformas open-source e ambientes altamente gerenciáveis, este blog é pra você. Se você não sabe o que é computação, quer começar a entender melhor como funciona e não quer ter o trabalho de traduzir manuais e how-to's, este blog também é para você!

Atualmente, o Papo de Cloud possui {{ site.posts | size }} posts em {{ site.categories | size }} categorias, que combinados possuem um total de {{ total_words }} palavras. Temos <a href="{{ site.url }}/destaques">{{ featuredcount }} posts em destaque</a> que merecem uma atenção especial, e o nosso post mais recente é {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Leia mais sobre {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %}.

## Sobre os criadores

<br>
<div class="author-info">
    <div class="row">
        <section class="notepad-post-author small-12 columns">
                <img src="{{site.url}}/images/writers/brunoemer.png" class="notepad-post-author-avatar" alt="Bruno Emer">
                <h2>Bruno Emer</h2>
                <p>Cofundador da Omnize e idealizador do Papo de Cloud. Fascinado por tecnologia, música e fotografia. Adora viajar e conhecer novas culturas, culinárias e idiomas. Gosta de futebol americano e torce para os Denver Broncos.</p>
        </section>
    </div>
</div>


<div class="author-info">
    <div class="row">
        <section class="notepad-post-author small-12 columns">
                <img src="{{site.url}}/images/writers/gilmarmachado.png" class="notepad-post-author-avatar" alt="Gilmar Machado">
                <h2>Gilmar Machado</h2>
                <p>Analista de infraestrutura na Universidade de São Paulo e co-criador do Papo de Cloud. Acredita que a melhor solução é a que resolve o problema, estuda tudo o que encontra sobre web-scale IT e assiste a qualquer modalidade de esporte, apesar de não praticar nenhum.</p>
        </section>
    </div>
</div>
