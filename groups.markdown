---
layout: page
image_header: 
intro: We are made of four groups that lead visualization research in Geographic Information Systems, Human Centered AI, Visual Analytics and Information Visualization.
title: Our Groups
headtitle: Groups | Georgia Tech Visualization Lab
permalink: /groups/
---
<div id="groups">
    {% for group in site.groups %}
    {% assign remainder = forloop.index | modulo: 2 %}
    <div class="row">
        {%  if remainder ==  0 %}
        <div class="col-lg-4"></div>
        {% endif %}
        <div class="col-lg-8">
            <div class="card">
                <div class="card-body">
                    <div class="row">
                        <div class="col-lg-12">
                            <img alt="Picture of {{ group.name }}" class="img-center" src="{{ group.logo | prepend: site.baseurl }}"/>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-lg-6">
                            <p class="group-description">
                                {{ group.content | markdownify }}
                            </p>
                            {% if group.projects.size > 0 %}
                            <p><b>Featured Projects:</b></p>
                            <p>
                            <ul>
                            {% for project in group.projects %}
                                <li>
                                {% if project.link != null %}
                                <a target="_blank" href="{{ project.link }}">{{ project.title }}</a>
                                {% else %}
                                {{ project.title }}
                                {% endif %}
                                <br/></li>
                            {% endfor %}
                            </ul>
                            </p>
                            {% endif %}
                        </div>
                        <div class="col-lg-6">
                            <img class="w-100 vspace-sm-fixed" alt="Picture of {{ group.name }}'s fun moments" src="{{ group.spotlight_image | prepend: site.baseurl }}"/>
                            <br/>
                            <div class="tags">
                            {% for keyword in group.keywords %}
                                <span class="badge badge-secondary"> {{ keyword }} </span>
                            {% endfor %}
                            </div>
                        </div>
                    </div>
                    <br/>
                    <div class="row">
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
            </div>
        </div>
        {%  if remainder !=  0 %}
        <div class="col-lg-4"></div>
        {% endif %}
    </div>
    <br />
    {% endfor %}
</div>