---
layout: page
image_header: 
intro: We actively publish at premier conferences and journals in Visualization, Human Computer Interaction, Geographic Information Systems, Machine Learning, and Data Mining.
title: Our Publications
headtitle: Publications | Georgia Tech Visualization Lab
permalink: /publications/
---
<div class="banner">
    <p>
        If you have new publications with at least one of the core faculty members as collaborators, add them by following <a target="_blank" href="https://github.com/gtvis/gtvis.github.io">these instructions</a>.
    </p>
</div>
<div class="vspace-md-fixed"></div>
<form class="form">
    <div class="row">
        <div class="col-lg-2 col-md-6 col-sm-6 mb-2">
            <label for="sTitle">Title</label>
            <select class="form-control mr-sm-2 mb-2" type="text" id="sTitle" name="sTitle" placeholder="Title" multiple></select>
        </div>
        <div class="col-lg-2 col-md-6 col-sm-6 mb-2">
            <label for="sAuthor">Author</label>
            <select class="form-control mr-sm-2 mb-2" id="sAuthor" name="sAuthor" placeholder="Author" multiple></select>
        </div>
        <div class="col-lg-4 col-md-12 col-sm-12 mb-2">
            <label for="sYear">Year</label>
            <div class="mr-sm-2 mb-2" id="sYear" name="sYear">
                <div id="custom-handle1" class="ui-slider-handle"></div>
                <div id="custom-handle2" class="ui-slider-handle"></div>
            </div>
        </div>
        <div class="col-lg-2 col-md-6 col-sm-6 mb-2">
            <label for="sVenue">Venue</label>
            <select class="form-control mr-sm-2 mb-2" id="sVenue" name="sVenue" placeholder="Venue" multiple></select>
        </div>
        <div class="col-lg-2 col-md-6 col-sm-6 mb-2">
            <label for="sTag">Tag</label>
            <select class="form-control mr-sm-2 mb-2" type="text" id="sTag" name="sTag" placeholder="Tag" multiple></select>
        </div>
    </div>
    <div class="row">
        <div class="col">
            <label class="sr-only" for="clearBtn"></label>
            <a id="clearBtn" href="javascript:clear();">
                clear all filters
            </a>
        </div>
    </div>
</form>

<br/><br/>

<div id="publications" class="row">
    {% assign sorted-publications = site.publications | sort: 'year' | reverse %}
    {% for publication in sorted-publications %}
    <div class="publication col-lg-12" data-pub-id="{{ forloop.index0 }}">
        <h5 class="caps">{{ publication.title }}</h5>
        <div class="authors">
            {% for author in publication.authors %}
                <span class="caps">{{ author }}</span>{% if forloop.last %}{% else %}<span>,</span>{% endif %}
            {% endfor %}
        </div>
        <div>
            {% for tag in publication.tags %}
                <span class="badge badge-secondary caps"> {{ tag }} </span>
            {% endfor %}
            {% if publication.tags.size > 0 %}
            <div class="vspace-xs-fixed"></div>
            {% endif %}
        </div>
        <div class="venue caps"><i>{{ publication.venue }} {{ publication.year }}</i></div>
        <div>
            <!-- Commenting this out because DBLP and our current publications source does not have links for all publications. Google Scholar is more reliable. -->
            <!-- {% if publication.link != null %}
                <a href="{{ publication.link }}" target="_blank"><i class="fa fa-external-link"></i></a>
            {% endif %} -->
            {% assign encodedTitle = publication.title | url_encode %}
            {% assign gscholarLink = 'https://scholar.google.com/scholar?hl=en&q=' | append: encodedTitle %}
            <a href="{{ gscholarLink }}" target="_blank">Google Scholar&nbsp;<i class="fa fa-external-link"></i></a>
        </div>
        <div class="separator"></div>
    </div>
    {% endfor %}
</div>

<script>
    const pubsData = {{sorted-publications | jsonify }};
    const pubsEl = document.querySelectorAll('.publication');
    const sAuthorEl = $('#sAuthor');
    const sTitleEl = $('#sTitle');
    const sYearEl = $("#sYear");
    const sTagEl = $('#sTag');
    const sVenueEl = $('#sVenue');

    let minMaxYear = [Infinity, -Infinity];
    let uniqueTags = [];
    let tagOptions = [];
    let uniqueAuthors = [];
    let authorOptions = [];
    let uniqueVenues = [];
    let venueOptions = [];
    let uniqueTitles = [];
    let titleOptions = [];

    function init(){
        pubsEl.forEach(pubEl => {
            const pubIdx = parseInt($(pubEl).attr("data-pub-id"));
            const pubData = pubsData[pubIdx];

            // Unique Tags
            pubData.tags.forEach(function(tag){
                if(uniqueTags.indexOf(tag) === -1){
                    uniqueTags.push(tag);
                    tagOptions.push({id:tag, text:tag});
                }
            });

            // Unique Authors
            pubData.authors.forEach(function(author){
                if(uniqueAuthors.indexOf(author) === -1){
                    uniqueAuthors.push(author);
                    authorOptions.push({id: author, text:author});
                }
            });

            // Unique Venues
            if(uniqueVenues.indexOf(pubData.venue) === -1){
                uniqueVenues.push(pubData.venue);
                venueOptions.push({id: pubData.venue, text: pubData.venue});
            }

            // Unique Titles
            if(uniqueTitles.indexOf(pubData.title) === -1){
                uniqueTitles.push(pubData.title);
                titleOptions.push({id: pubData.title, text: pubData.title});
            }

            // Find the range of years
            const year = pubData.year;
            if(year < minMaxYear[0]){
                minMaxYear[0] = year;
            }
            if(year > minMaxYear[1]){
                minMaxYear[1] = year;
            }
        });

        // Initialize the slider
        var handle1 = $( "#custom-handle1" );
        var handle2 = $( "#custom-handle2" );
        sYearEl.slider({
            range: true,
            min: minMaxYear[0],
            max: minMaxYear[1],
            step: 1,
            values: minMaxYear,
            slide: function(event, ui) {
                handle1.text( ui.values[0] );
                handle2.text( ui.values[1] );
            },
            change: function(event, ui) {
                handle1.text( ui.values[0] );
                handle2.text( ui.values[1] );
                search();
            },
            create: function() {
                handle1.text( $( this ).slider( "values", 0 ) );
                handle2.text( $( this ).slider( "values", 1 ) );
            },
        });

        sAuthorEl.select2({
            tags: true,
            allowClear: true,
            placeholder: '',
            data: authorOptions
        });
        sAuthorEl.on('change', function (e) {
            search();
        });

        sVenueEl.select2({
            tags: true,
            allowClear: true,
            placeholder: '',
            data: venueOptions
        });
        sVenueEl.on('change', function (e) {
            search();
        });

        sTagEl.select2({
            tags: true,
            allowClear: true,
            placeholder: '',
            data: tagOptions
        });
        sTagEl.on('change', function (e) {
            search();
        });

        $(sTitleEl).select2({
            tags: true,
            allowClear: true,
            placeholder: '',
            data: titleOptions
        });
        $(sTitleEl).on('change', function (e) {
            search();
        });

    }

    function clear(){
        sYearEl.slider("values", minMaxYear);
        $(sAuthorEl).val(null).trigger('change');
        $(sTitleEl).val(null).trigger('change');
        $(sVenueEl).val(null).trigger('change');
        $(sTagEl).val(null).trigger('change');
        search();
    }

    function search() {
        const _sAuthor = sAuthorEl.select2('data');
        const _sTitle = sTitleEl.select2('data');
        const _sYear = sYearEl.slider("values");
        const _sTag = sTagEl.select2('data');
        const _sVenue = sVenueEl.select2('data');

        pubsEl.forEach(pubEl => {
            const pubIdx = parseInt($(pubEl).attr("data-pub-id"));
            const pubData = pubsData[pubIdx];
            let showPub = true;
            if(_sAuthor.length == 0 && _sVenue.length == 0 && _sTag.length == 0 && _sTitle.length == 0 && _sYear[0] == minMaxYear[0] && _sYear[1] == minMaxYear[1]){
                showPub = true;
            }else{
                if(_sAuthor.length > 0){
                    if(pubData.authors.length > 0){
                        if(!_sAuthor.some(valObj => pubData.authors.includes(valObj.text))){
                            showPub = false;
                        }
                    }else{
                        showPub = false;
                    }
                }
                if(_sVenue.length > 0){
                    if(!_sVenue.some(valObj => pubData.venue == valObj.text)){
                        showPub = false;
                    }
                }
                if(_sTag.length > 0){
                    if(pubData.tags.length > 0){
                        if(!_sTag.some(valObj => pubData.tags.includes(valObj.text))){
                            showPub = false;
                        }
                    } else{
                        showPub = false;
                    }
                }
                if(_sTitle.length > 0){
                    if(!_sTitle.some(valObj => pubData.title == valObj.text)){
                        showPub = false;
                    }
                }
                if(parseInt(pubData.year) < _sYear[0] || parseInt(pubData.year) > _sYear[1]){
                    showPub = false;
                }
            }
            pubEl.style.display = showPub ? "block" : "none";
        });
    }

    init();

</script>