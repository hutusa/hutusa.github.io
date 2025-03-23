---
date: '{{ .Date }}'
author: ["Lisa Zhong"]
title: {{ replaceRE "^[0-9]{4}-[0-9]{2}-[0-9]{2}-" "" .File.BaseFileName | humanize | title }}
slug: {{ replaceRE "^[0-9]{4}-[0-9]{2}-[0-9]{2}-" "" .File.BaseFileName | urlize }}
summary: "Sample article."
tags: ["blog", "podcast"]
categories: ["blog"]
---
