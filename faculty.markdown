---
layout: page
image_header: 
intro: 
title: Our Faculty
headtitle: Faculty | Georgia Tech Visualization Lab
permalink: /faculty/
---
<div id="faculty" class="row">
    {% assign core-faculty = site.faculty | where_exp:"faculty",
    "faculty.type == 'core'" %}
    {% for person in core-faculty %}
    <div class="col-lg-6 col-md-6 col-sm-6 large-card-container">
        <div class="large-card">
            <div class="row no-gutters">
                <div class="col-lg-5 col-md-12 col-sm-12"> 
                    <img class="w-100" alt="Picture of {{ person.image }}" src="{{ person.image | prepend: site.baseurl }}"/>
                </div>
                <div class="col-lg-7 col-md-12 col-sm-12">
                    <div class="description p-l-md">
                        <h2>
                            {{ person.name }}                    
                        </h2>
                        <h3>{{ person.role }}</h3>
                        <br />
                        <div class="tags">
                        {% for keyword in person.keywords %}
                            <span class="badge badge-secondary"> {{ keyword }} </span>
                        {% endfor %}
                        </div>
                        <br/><br/>
                        <div class="sc-links">
                            {% if person.website %}
                            <a target="_blank" href="{{ person.website }}"><i class="fa fa-globe"></i></a>
                            {% endif %}
                            {% if person.email %}
                            <a target="_blank" href="mailto: {{ person.email }}"><i class="fa fa-envelope"></i></a>
                            {% endif %}
                            {% if person.linkedin %}
                            <a target="_blank" href="{{ person.linkedin }}"><i class="fa fa-linkedin"></i></a>
                            {% endif %}
                            {% if person.twitter %}
                            <a target="_blank" href="{{ person.twitter }}"><i class="fa fa-twitter"></i></a>
                            {% endif %}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    {% endfor %}
</div>
<div class="vspace-lg"></div>
<div class="row">
    <h3 class="col-lg-12">Affiliated Faculty</h3>
</div>
<div id="affiliated-faculty" class="row">
    {% assign aff-faculty = site.faculty | where_exp:"faculty",
    "faculty.type == 'affiliate'" %}
    {% for person in aff-faculty %}
    <div class="col-lg-4 col-md-6 col-sm-6 medium-card-container">
        <div class="medium-card">
            <div class="row no-gutters">
                <div class="col-lg-5">
                    <img class="w-100" alt="Picture of {{ person.name }}" src="{{ person.image | prepend: site.baseurl }}"/>
                </div>
                <div class="col-lg-7">
                    <div class="description p-l-sm">
                        <h2> 
                            {{ person.name }}
                        </h2>
                        <h3> {{ person.role }}
                        </h3>
                        <br/>
                        <div class="sc-links">
                            {% if person.website %}
                            <a target="_blank" href="{{ person.website }}"><i class="fa fa-globe"></i></a>
                            {% endif %}
                            {% if person.email %}
                            <a target="_blank" href="mailto: {{ person.email }}"><i class="fa fa-envelope"></i></a>
                            {% endif %}
                            {% if person.linkedin %}
                            <a target="_blank" href="{{ person.linkedin }}"><i class="fa fa-linkedin"></i></a>
                            {% endif %}
                            {% if person.twitter %}
                            <a target="_blank" href="{{ person.twitter }}"><i class="fa fa-twitter"></i></a>
                            {% endif %}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    {% endfor %}
</div>