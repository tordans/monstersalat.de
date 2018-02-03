
# TODO
- favicon
- google analytics
- twitter card
- facebook
- 404 Page

---------


# Links

- Admin UI https://github.com/jekyll/jekyll-admin

- Sitemap? https://github.com/jekyll/jekyll-sitemap

- Maybe Seo Plugin https://github.com/jekyll/jekyll-seo-tag

- könnte gute tipps seite sein http://jekyll.tips/

- Formular erstellen https://getsimpleform.com/
- Github pages docu https://help.github.com/categories/github-pages-basics/
- Beispiele für Jekyll Sites mit Source Code http://jekyllrb.com/docs/sites/

- doku für liquid / foreach schleifen https://github.com/Shopify/liquid/wiki/Liquid-for-Designers#for-loops

- posts nach kategorie filtern http://stackoverflow.com/a/25073401/729221
  {% for page in site.pages %}
    {% if page.categories contains 'fruit' %}
      <div class="item">
        <h3>{{page.title}}</h3>
        <p>{{page.description}}</p>
      </div>
    {% endif %}
  {% endfor %}
- posts nach gewicht ausgeben http://stackoverflow.com/a/30274671/729221

- post_url slug
  http://stackoverflow.com/a/31483469/729221

- Liste aller Funktionen auf einer Seite
  http://ricostacruz.com/cheatsheets/jekyll.html

- Extending Jekyll with Ruby for TagsPerPage
  http://brizzled.clapper.org/blog/2010/12/20/some-jekyll-hacks/
- Another one, but better?
  http://charliepark.org/tags-in-jekyll/
  https://github.com/charliepark/charliepark.github.com/blob/master/_plugins/tag_gen.rb

- Tag liste nur mit Liquid / ohne Plugin
  http://blog.lanyonm.org/articles/2013/11/21/alphabetize-jekyll-page-tags-pure-liquid.html
  https://github.com/LanyonM/lanyonm.github.io/blob/master/tags.html
  http://blog.lanyonm.org/tags.html
  Problem: Das Plugin verwendet nur die tags aus den blogposts, nicht aus eine collection.
  Und auf die scheine ich keinen Zugriff zu haben.

- Wie man den ganzen Prozess lokal automatisieren könnte
  Mit Custom Plugin, lokal generieren, bei Github ausspielen
  http://charliepark.org/jekyll-with-plugins/

- Verwendet:
  Unique Tag List aller Artikel erstellen
  http://stackoverflow.com/questions/34242743/distinct-in-jekyll-liquid





------

# Bis auf weiteres nicht verwendet:

      ---
      layout: page
      ---

      # Alle Anlässe

      {% capture all_product_tags_raw %}
        {% for produkt in site.produkte %}
            {% for tag in produkt.tags %}
              {{ tag }},
            {% endfor %}
        {% endfor %}
      {% endcapture %}

      {% assign all_product_tags_with_duplicates = all_product_tags_raw | strip_newlines | split: ',' | sort %}

      {% assign all_product_tags_unique = '' | split: ',' %}
      {% for tag in all_product_tags_with_duplicates %}
        {% assign tag_for_comparison = tag | slugify %}
        {% unless tag_for_comparison == previous_tag %}
          {% assign all_product_tags_unique = all_product_tags_unique | push: tag %}
        {% endunless %}
        {% assign previous_tag = tag | slugify %}
      {% endfor %}

      all_product_tags_unique:
      {{ all_product_tags_unique }}

      <!--
      {% for tag in site.homepage.ordered_tags_lists.primary %}
        <h2>{{ tag }}</h2>
        <div class="row">
          {% for produkt in site.produkte %}
            {% for product_tag in produkt.tags %}
              {% if product_tag == tag %}
                <a class="col-md-6" href="{{ produkt.url }}" title="{{ produkt.title }}">
                  <img src="/produkte/{{ produkt.image_path }}/main.jpeg" style="width:100%" title="{{ produkt.title }}">
                </a>
              {% endif %}
            {% endfor %}
          {% endfor %}
        </div>
      {% endfor %}
       -->



