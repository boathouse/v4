---
layout: default
---

<head>
    <meta charset="utf-8">
    <title>{{ site.name }}</title>
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no, width=device-width">
    <meta name="description" content="{{ site.description }}">
    <meta name="theme-color" content="#1a1a1a">
    <link rel="icon" href="/assets/icons/favicon.ico">
	<link rel="stylesheet" href="/assets/css/local/style.css">
    <style type="text/css"></style>
{% comment %}<!-- <link rel="apple-touch-icon" sizes="180x180" href="/assets/icons/apple-touch-icon.png">
    <link rel="manifest" href="/manifest.json"> -->
{% endcomment %}
</head>
<body>
	<div class="clearfix header">
		<div class="main-container">
			<div class="website clearfix">
				<a href="/" target="_blank"><img src="assets/icons/logo.png"> {{ site.name }}</a>
			</div>
			<div class="logo">
				<div class="search-form clearfix">
					<form id="searchform1" name="searchform1" action="/" method="get">                    
						<input name="s" type="text" class="srchTxt">
						<input type="submit" class="srchBtn" value="">
					</form>
				</div>
			</div>
		</div>
	</div>
	<!--  -->
	<div class="main-container" id="main">
		<div class="popular-searches clearfix">
			<div class="frame-container">
				<div class="photo-box" data-model="seafisher480"></div>
				<div class="mod-nav" data-bind="template: {name: 'modnav'}"></div>
				<div class="mod3d" data-bind="template: {name: 'mod3d'}"></div>
			</div>
{% comment %}
			<ul class="clearfix first">
				<li><a href="" title="">3D Models</a></li>
				<li><a href="" title="">Тест кнопка</a></li>
				<li><a href="" title="">Воат АШЫРУК</a></li>
				<li><a href="" title="">лодка FISHER</a></li>
				<li><a href="" title="">3D TRAVEL</a></li>
				<li><a href="" title="">БАМБАРБЕА</a></li>
			</ul>
{% endcomment %}
			<div class="footer-related clearfix">
				<ul class="clearfix bottom">
					<li class="hdMbN"><span>Related links: </span></li>
					<li><a href="" title="">3D Boat Models</a></li>
					<li><a href="" title="">лодка FISHER</a></li>
					<li><a href="" title="">3D TRAVEL</a></li>
				</ul>
			</div>
		</div>
		<ul class="privacy clearfix">
			<li><a href="#" target="_blank">Privacy Policy</a></li>
		</ul>
	</div>

{% for model in site.data.demo %}
    <div class="btn onw3d_btn" data-model="{{ model.model }}">{{ model.name }}</div>
{% endfor %}

<!-- Templates (temporary) -->
<template id="mod3d"><div class="mod-cont">
<div class="mod-info">
    <span>Комплектация: <b class="mod-name" data-bind="text: modName"> </b> <i class="mod-price" data-bind="text: '$' + parseInt(modPrice()), visible: modPrice() > 0"></i></span> 
    <span class="more" data-bind="html: moreBtn, click: detailsMode, visible: modName() != baseName"></span>
</div>
<div class="mod-details">
    <ol data-bind="foreach: goodsList, visible: modName() != baseName">
        <li><span data-bind="text: name"></span> <span class="good-price" data-bind="text: '$' + parseInt(price)"></span></li>
    </ol>
    <p class="mod-info" data-bind="visible: modName() != baseName">
        <span>Стоимость: <i class="mod-price" data-bind="text: '$' + parseInt(modPrice())"></i></span>
    </p>
</div>
</div></template>

<template id="modnav">
<div class="mod-list" data-bind="foreach: modsList">
    <div data-bind="class: $parent.isActive(), attr: {'data-name': name}">
        <b data-bind="text: name"></b>
    </div>
</div>
</template>

{% comment %}
    style="background-image: url(https://boathouse.ua/{{ model.icon }})"
    <!-- <script>{% include_relative assets/js/onw3d.js %}</script> -->
{% endcomment %}
    <script src="/assets/js/web/onw3d.js"></script>
</body>