---
title: "CMPTGCS 20B: CS for Non Majors (2nd Course)"
---

# {{page.title}}

Welcome to {{site.course}}!

<div id="info" data-role="collapsible" data-collapsed="false">
<h2>Course Information</h2>
<ul>
{% for item in site.info %}
<li><a href="{{item.url | relative_url}}"  data-ajax="false">{{item.title }}</a></li>
{% endfor %}
</ul>
</div>

<!-- labs -->
{% include collapse-card-begin.html label="Labs" id="labs" %}
## Labs
{% include lab_table.html %}
{% include collapse-card-end.html %}
<!-- end-labs -->

