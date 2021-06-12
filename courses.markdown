---
layout: page
image_header: 
intro: We offer classes in Information Visualization and Visual Analytics for undergraduates as well as graduates in the Spring and Fall semesters.

title: Our Courses
headtitle: Courses | Georgia Tech Visualization Lab
permalink: /courses/
---
<div id="courses">
    <div class="row vspace-md-fixed">
        <div class="col-lg-1"></div>
        {% assign levels = "Undergraduate, Graduate" | split: ', ' %}
        {% for level in levels %}
        <div class="col-lg-5 mb-4">
            <div class="row">
                <div class="col-lg-12">
                    <h3>{{level}}</h3>
                    <div class="vspace-lg-fixed"></div>
                </div>
            </div>
            {% assign cs_courses = site.courses | where_exp: "course", "course.code contains 'CS '" | sort: "code" %}
            {% assign cx_courses = site.courses | where_exp: "course", "course.code contains 'CX '" | sort: "code" %}
            {% assign cse_courses = site.courses | where_exp: "course", "course.code contains 'CSE '" | sort: "code" %}
            {% assign cp_courses = site.courses | where_exp: "course", "course.code contains 'CP '" | sort: "code" %}
            {% assign sorted-courses = cs_courses | concat: cse_courses | concat: cx_courses | concat: cp_courses  %}
            {% for course in sorted-courses %}
            <div>
                {% if course.level == level %}
                <div class="card">
                    <div class="title">{{ course.code }} : {{ course.name }}</div>
                    <div class="tags">
                        {% for tag in course.tags %}
                        <span class="badge badge-secondary"> {{ tag }} </span>
                        {% endfor %}
                    </div>       
                    <div class="course-details-inactive">
                        <p>{{ course.content | markdownify }}</p>
                        {% assign recent_offering = course.offerings | first %}
                        <table class="table-course-offerings">
                            <tr>
                                <td><i class="fa fa-play theme-icon"></i>Recent Offering</td>
                                <td><a target="_blank" href="{{ recent_offering.link }}">{{ recent_offering.semester }} {{ recent_offering.year }}</a> ({% for instructor in recent_offering.instructors %}{{ instructor }}){% endfor %}
                                </td>
                            </tr>
                            <tr>
                                <td><i class="fa fa-history theme-icon"></i>Past Offering(s)</td>
                                <td>
                                {% for offering in course.offerings %}
                                    {% if forloop.first != true %}
                                        <a target="_blank" href="{{ offering.link }}">{{ offering.semester }} {{ offering.year }}</a> {% unless forloop.last %} | {% endunless %} 
                                    {% endif %}
                                {% endfor %}
                                </td>
                            </tr>
                            <tr>
                                <td><i class="fa fa-arrow-right theme-icon"></i>Next Offering</td>
                                <td>{{ course.next_offering }}</td>
                            </tr>
                        </table>
                    </div>
                </div>
                {% endif %}
            </div>
            {% endfor %}
        </div>
        {% endfor %}
        <div class="col-lg-1"></div>
    </div>
</div>
    

<script>
    $('.card').click(e => {
        if ($(e.currentTarget).hasClass('card-active')) {
            $(e.currentTarget).removeClass('card-active');
            $(e.currentTarget.children[2]).removeClass('course-details-active');
        } else {
            $('#courses .card').removeClass('card-active');
            $('.course-details-inactive').removeClass('course-details-active');
            $(e.currentTarget).addClass('card-active');
            $(e.currentTarget.children[2]).addClass('course-details-active');
        }
    });

    $('.card a').on("click", function(event) {
        event.stopPropagation();
    });

</script>