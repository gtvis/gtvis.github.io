---
layout: page
image: 
intro: Our research has been made possible by support and funding from the below sources.
title: Our Sponsors
headtitle: Sponsors | Georgia Tech Visualization Lab
permalink: /sponsors/
---
<div id="sponsors">
    <div class="row">
        {% for sponsor in site.data.sponsors %}
            <div class="col-lg-2 col-md-3 col-sm-4 col-4">
                <div class="sponsor-container">
                    <a title="{{ sponsor.name }}" href="{{ sponsor.website }}" target="_blank">
                        <img class="card-img-top mx-auto d-block" src="{{ sponsor.image | prepend: site.baseurl }}" alt="Picture of {{ sponsor.name }}">
                    </a>
                </div>
            </div>
        {% endfor %}
    </div>
</div>