---
author: livingmethod
comments: true
date: 2014-07-26 03:08:19+00:00
layout: post
link: http://blog.jblee.kr/2014/07/26/nginx-virtual-host-%ea%b5%ac%ec%84%b1/
slug: nginx-virtual-host-%ea%b5%ac%ec%84%b1
title: Nginx Virtual Host 구성?
wordpress_id: 22
---

#####################new

server {
	listen 80; ## listen for ipv4; this line is default and implied
	#listen [::]:80 default_server ipv6only=on; ## listen for ipv6

	root /disk/movie/;
	index index.html index.htm;

	# Make site accessible from http://localhost/
	server_name [서버주소];

	location / {
		# First attempt to serve request as file, then
		# as directory, then fall back to displaying a 404.
		try_files $uri $uri/ /index.html;
		# Uncomment to enable naxsi on this location
		# include /etc/nginx/naxsi.rules
	}
		autoindex on;
		allow 127.0.0.1;
		allow ::1;
		deny all;
	}

	# Only for nginx-naxsi used with nginx-naxsi-ui : process denied requests
	#location /RequestDenied {
	#	proxy_pass http://127.0.0.1:8080; 
	#}

	#error_page 404 /404.html;

	# redirect server error pages to the static page /50x.html
	#
	#error_page 500 502 503 504 /50x.html;
	#location = /50x.html {
	#	root /usr/share/nginx/www;
	#}

##################newend

이렇게 기본이기에 바꿔서 해도 안되네..
