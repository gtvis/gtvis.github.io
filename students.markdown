---
layout: page
image_header: 
intro: 
title: Our Students
headtitle: Students | Georgia Tech Visualization Lab
permalink: /students/
---
<div id="students">
    <div class="filter">
        <div>
            <a class="active-selection" id="all">ALL</a>
            <a id="PhD">PHD</a>
            <a id="MS">MS</a>
            <a id="BS">BS</a>
            <a id="PostDoc">POST&nbsp;DOC</a>
        </div>
    </div>
    {% assign sorted-students = site.students | sort: "name" | where_exp:"student",
    "student.graduation_year == undefined" %}
    <div id="curr-stud-header" style="margin-bottom: 64px;">
        <div class="row">
            <h3 class="col-lg-12">Current Students</h3>
        </div>
        <div class="row">
        {% for person in sorted-students %}
            <div class="col-lg-3 col-md-3 col-sm-3 col-6 mini-card-container" category="{{ person.degree_level }}" type="curr-student">
                <div class="mini-card">
                    <div class="row no-gutters">
                        <div class="col-lg-5 col-md-12 col-sm-12">
                            <img class="w-100" alt="Picture of {{ person.name }}" src="{{ person.image | prepend: site.baseurl }}"/>
                        </div>
                        <div class="col-lg-7 col-md-12 col-sm-12">
                            <div class="p-l-sm">
                                <h2> 
                                    {{ person.name }}
                                </h2>
                                <h3> 
                                    {{ person.degree_level }} {{ person.major }}
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
    </div>
    <div id="alumni-header">
        <div class="row">
            <h3 class="col-lg-12">Alumni</h3>
        </div>
        <div class="row">
            {% assign filtered-students = site.students | where_exp:"student", "student.graduation_year != undefined" | sort: "graduation_year" | reverse %}
            {% assign grouped-students = filtered-students | group_by: "graduation_year" %}
            {% for student-group in grouped-students %}
                {% assign fall_alums = student-group.items | where_exp: "alum", "alum.graduation_semester contains 'Fall'" | sort: "name" | reverse %}
                {% assign summer_alums = student-group.items | where_exp: "alum", "alum.graduation_semester contains 'Summer'" | sort: "name" | reverse %}
                {% assign spring_alums = student-group.items | where_exp: "alum", "alum.graduation_semester contains 'Spring'" | sort: "name" | reverse %}
                {% assign sorted-students = fall_alums | concat: summer_alums | concat: spring_alums  %}
                {% for person in sorted-students %}
                <div class="col-lg-3 col-md-3 col-sm-3 col-6 mini-card-container" category="{{ person.degree_level }}" type="alumni">
                    <div class="mini-card">
                        <div class="row no-gutters">
                            <div class="col-lg-5 col-md-12 col-sm-12">
                                <img class="w-100" alt="Picture of {{ person.name }}" src="{{ person.image | prepend: site.baseurl}}"/>
                            </div>
                            <div class="col-lg-7 col-md-12 col-sm-12">
                                <div class="p-l-sm">
                                    <h2>
                                        {{ person.name }}
                                    </h2>
                                    <h3> 
                                        {{ person.role }} 
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
            {% endfor %}
        </div>
    </div>  
</div>
<div class="vspace-md"></div>
<div class="row" >
    <div class="col-lg-12">
        <div id="banner">
            <p>
                If you want to be listed here, please contact any of the faculty members.
            </p>
        </div>
    </div>
</div>

<script>
    $('.filter a').click(e => {
        $('.filter a').removeClass('active-selection');
        $(e.currentTarget).addClass('active-selection');
        $('.mini-card-container').css('display', 'none');
        if (e.currentTarget.id == "all") {
            $('.mini-card-container').css('display', 'block');
        } else {
            $(`div[category = '${e.currentTarget.id}']`).css('display', 'block');
        }
        if($(`div[category = '${e.currentTarget.id}'][type = 'curr-student']`).length == 0 && e.currentTarget.id != "all") {
            $('#curr-stud-header').css('display', 'none');
        } else {
            $('#curr-stud-header').css('display', 'block');
        }


        if($(`div[category = '${e.currentTarget.id}'][type = 'alumni']`).length == 0 && e.currentTarget.id != "all") {
            $('#alumni-header').css('display', 'none');
        } else {
            $('#alumni-header').css('display', 'block');
        }
    });
</script>