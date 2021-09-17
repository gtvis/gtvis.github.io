---
layout: page
image_header:
intro: 
title: Our News and Events
headtitle: News and Events | Georgia Tech Visualization Lab
permalink: /news/
---
<div class="banner">
    <p>
        If you have news items to publish, add them by following <a target="_blank" href="https://github.com/gtvis/gtvis.github.io">these instructions</a>.
    </p>
</div>
<div class="vspace-md-fixed"></div>
<div id="news" class="mob-hide row">
    <div class="col-lg-6">
        {% assign sorted-news = site.data.news | sort: '_date' | reverse %}
        {% for news in sorted-news %}
        {% assign mod = forloop.index | modulo: 2 %}
        {% if mod == 1 %}
        <div class="news-item">
            <div class="row">
                <div class="col-lg-12">           
                    <div class="title">{{ news.title }}</div>
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-7 short-description-container">
                    <p class="short-description collapsed"><span class="font-weight-bold">{{ news._date }}:</span>
                        {{ news.short_description }}</p>
                </div>
                <div class="col-lg-5 thumbnail-container">
                    <img class="thumbnail" alt="Picture of {{ news.image }}"
                        src="{{ news.image | prepend: site.baseurl }}" />
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <p class="description">{{ news.description }}</p>
                </div>
            </div>
        </div>
        {% endif %}
        {% endfor %}
    </div>
    <div class="col-lg-6" style="margin-top: 80px">
        {% assign sorted-news = site.data.news | sort: '_date' | reverse %}
        {% for news in sorted-news %}
        {% assign mod = forloop.index | modulo: 2 %}
        {% if mod == 0 %}
        <div class="news-item">
            <div class="row">
                <div class="col-lg-12">           
                    <div class="title">{{ news.title }}</div>
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-7 short-description-container">
                    <p class="short-description collapsed"><span class="font-weight-bold">{{ news._date }}:</span>
                        {{ news.short_description }}</p>
                </div>
                <div class="col-lg-5 thumbnail-container">
                    <img class="thumbnail" alt="Picture of {{ news.image }}"
                        src="{{ news.image | prepend: site.baseurl }}" />
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <p class="description">{{ news.description }}</p>
                </div>
            </div>
        </div>
        {% endif %}
        {% endfor %}
    </div>
</div>

<div id="news" class="mob-only row">
    <div class="col-lg-12">
        {% assign sorted-news = site.data.news | sort: '_date' | reverse %}
        {% for news in sorted-news %}
        <div class="news-item">
            <div class="row">
                <div class="col-lg-12">           
                    <div class="title">{{ news.title }}</div>        
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <p class="short-description collapsed"><span class="font-weight-bold">{{ news._date }}:</span>
                        {{ news.short_description }}</p>
                </div>
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <img class="thumbnail" alt="Picture of {{ news.image }}"
                        src="{{ news.image | prepend: site.baseurl }}" />
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <p class="description">{{ news.description }}</p>
                </div>
            </div>
        </div> 
        {% endfor %}
    </div>
</div>

<script>
    $('.news-item').click(e => {

        if ($(e.currentTarget).hasClass('active-news-item')) {
            $(e.currentTarget).removeClass('active-news-item');
            $('.news-item .description').css('display', 'none');
            $('.short-description').addClass('collapsed');

            $('.thumbnail-container').removeClass('col-lg-12');
            $('.thumbnail-container').addClass('col-lg-5');
            $('.short-description-container').removeClass('col-lg-12');
            $('.short-description-container').addClass('col-lg-5');
        } else {
            $('.news-item').removeClass('active-news-item');
            $(e.currentTarget).addClass('active-news-item');

            $('.news-item .description').css('display', 'none');

            $(e.currentTarget).find('.description').css('display', 'block');
            $(e.currentTarget).find('.collapsed').removeClass('collapsed');
            
            $('.thumbnail-container').removeClass('col-lg-12');
            $('.thumbnail-container').addClass('col-lg-5');

            $(e.currentTarget).find('.thumbnail-container').removeClass('col-lg-5');
            $(e.currentTarget).find('.thumbnail-container').addClass('col-lg-12');
            
            $('.short-description-container').removeClass('col-lg-12');
            $('.short-description-container').addClass('col-lg-5');
            $(e.currentTarget).find('.short-description-container').removeClass('col-lg-5');
            $(e.currentTarget).find('.short-description-container').addClass('col-lg-12');
        }
    });
</script>