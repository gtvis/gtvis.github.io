---
layout: page
image: /assets/images/logo_bluegold_aspect_2_1.png
image_header: /assets/images/logo_bluegold.png
title: # Leave it blank
headtitle: Home | Georgia Tech Visualization Lab
permalink: /
---
<div id="home">
  <div class="row">
    <div class="col-lg-5">
      <div class="vspace-md"></div>
      <p>
        <span id="welcome">Welcome!</span> We are the home for visualization research at the Georgia Institute of Technology. Our mission is to empower everyone to analyze and communicate data with interactive systems.
      </p>
      <p>
        The team is made up of four groups that lead visualization research in <b>Information Visualization, Human-Computer Interaction, Visual Analytics,</b> and <b>Geographic Information Systems</b>.
      </p>
      <p>
      <div id="scroll-text"><i class="fa fa-arrow-down"></i>&nbsp;&nbsp;Scroll to see more!&nbsp;&nbsp;<i class="fa fa-arrow-down"></i></div>
      </p>
    </div>
    <!-- <div class="col-lg-1"></div> -->
    <div class="col-lg-7">
      <div class="carousel">
       {% for item in site.data.gallery %}
          <div>
          <img class="w-100" alt="Picture of {{ item.image }}" src="{{ item.image | prepend: site.baseurl }}" />
          <p>{{ item.description }}</p>
          </div>
        {% endfor %}
      </div>
    </div>
  </div>
  <div class="vspace-lg"></div>
  <div class="row">
    {% for group in site.groups %}
      <div class="col-lg-3 col-md-12 col-sm-12">
        <div class="card">
        <a target="_blank" href="{{ group.website }}">
          <div class="card-img-top">
            <img class="card-img" alt="Picture of {{ group.logo }}" src="{{ group.logo | prepend: site.baseurl }}" alt="{{ group.name }}">
          </div>
          <div class="card-body">
            <h5 class="group-name text-center">
                {{group.name}}&nbsp;
            </h5>
            <div class="card-text">              
              <hr>
              {% for professor in group.professors %}
              <h2 class="group-professor">{{professor }}</h2>
              {% endfor %}
              {{ group.headline | markdownify }}
              <div class="sc-links">
                  {% if group.website %}
                  <a target="_blank" href="{{ group.website }}"><i class="fa fa-globe"></i></a>
                  {% endif %}
                  {% if group.github %}
                  <a target="_blank" href="{{ group.github }}"><i class="fa fa-github"></i></a>
                  {% endif %}
              </div>
            </div>
          </div>
          </a>
        </div>
      </div>
    {% endfor %}
  </div>
  <div class="vspace-lg"></div>
  <hr>
  <br/><br/>
  <div class="row">
    <h3 class="col-lg-12 text-center">
      Recent news from the lab!
    </h3>
  </div>
  <br/>
  <div class="row">
    <div class="col-lg-6 col-md-12 col-sm-12 mob-hide">
        {% assign sorted-news = site.data.news | sort: '_date' | reverse %}
        {% for news in sorted-news limit:3 %}
        <div class="news-item">
            <div class="row">
                <div class="col-lg-12">
                  <div class="title">{{ news.title }}</div>
                </div>
            </div>
            <br />
            <div class="row">
                <div class="col-lg-7 short-description-container">
                    <p class="short-description collapsed"><span class="font-weight-bold">{{ news._date | date: "%B %d, %Y"}}:</span>
                        {{ news.short_description }}</p>
                </div>
                <div class="thumbnail-container col-lg-5 ">
                    <img class="thumbnail" alt="Picture of {{ news.image }}"
                        src="{{ news.image | prepend: site.baseurl }}" />
                </div>
            </div>
            <br/>
            <div class="row">
                <div class="col-lg-12 col-md-12 col-sm-12">
                    <p class="description">{{ news.description }}</p>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
    <div class="col-lg-6 col-md-12 col-sm-12">
      <div class="twitter-container">
        <a class="twitter-timeline" data-height="740" href="https://twitter.com/GT_Vis?ref_src=twsrc%5Etfw">Tweets by GT_Vis</a> 
        <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
      </div>
    </div>
  </div>
</div>

<script>
  $('.carousel').slick({
    autoplay: true,
    arrows: false,
    autoplaySpeed: 4000,
    infinite: true,
    speed: 300,
    slidesToShow: 1
  });
</script>



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