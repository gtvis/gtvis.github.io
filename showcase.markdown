---
layout: page
image: 
title: Showcase
intro: Some of our lab's creations.
headtitle: Showcase | Georgia Tech Visualization Lab
permalink: /showcase/
---
<div id="gallery">
    <div class="row">
        <div class="col-lg-1"></div>
        <div class="col-lg-10">
            <div class="carousel">
            {% for item in site.data.showcase %}
                <div>
                <h2>{{ item.title }}</h2>
                <p>{{ item.description }}</p>
                <img class="w-100" alt="Picture of {{ item.image }}" src="{{ item.image | prepend: site.baseurl }}" />
                </div>
            {% endfor %}
            </div>
        </div>
        <div class="col-lg-1"></div>
    </div>  
    <div class="vspace-lg"></div>
    <div class="row">
        <div style="padding: 0px" class="col-lg-1 col-md-1 col-sm-1 col-1">
            <i class="fa fa-arrow-left"></i>
        </div>
        <div class="col-lg-10 col-md-10 col-sm-10 col-10">
            <div class="navigation mob-hide">
                {% for item in site.data.showcase %}
                    <div>
                    <!-- <p>{{ item.title }}</p> -->
                    <img class="w-100" alt="Picture of {{ item.image }}" src="{{ item.image | prepend: site.baseurl }}" />
                    </div>
                {% endfor %}
            </div>
        </div>
        <div style="padding: 0px" class="col-lg-1 col-md-1 col-sm-1 col-1">
            <i class="fa fa-arrow-right"></i>
        </div>
    </div>  
</div>

<script>

 $('.carousel').slick({
  slidesToShow: 1,
  slidesToScroll: 1,
  arrows: false,
  fade: true,
  asNavFor: '.navigation'
});

 $('.navigation').slick({
  slidesToShow: 3,
  slidesToScroll: 1,
  asNavFor: '.carousel',
  nextArrow: '.fa-arrow-right',
  prevArrow: '.fa-arrow-left',
//   dots: true,
  centerMode: true,
  focusOnSelect: true
});
</script>