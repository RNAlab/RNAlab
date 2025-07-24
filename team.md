---
layout: page
title: RNAlab Scientists
image:
  feature: bg/lab-candid.gif
---

<style>
* {
  box-sizing: border-box;
  }
/* Create three equal columns that floats next to each other */
.human {
  flex: 0 0 45%;
  width: 45%;
  padding: 10px;
  min-width: 320px;
  max-width: 430px;
  background-color: #ddd;
  border-radius: 3px;
  box-shadow: 0 0 0 0,0 6px 12px rgba(0,0,0,.1);
}

.group-counter {
  max-width: 95%;
  flex: 1;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 32px;
}

.profile-picture {
  width: 100px;
  height: 100px;
  object-fit: cover;
}

</style>

# Current

{% assign currentMembers = site.data.team | where:"current","true"  %}
{% assign alumniMembers = site.data.team | where:"current","false"  %}

<div style="display: flex; justify-content: center;">
  <div class="group-counter">
  {% for item in currentMembers %}
    {% assign imageHref = '/images/hu/' | append: item.image | prepend: site.baseurl %}
    {% if item.current %}
      <div class="human" style="{% if forloop.last %}flex:0.47;{% else %}flex:1;{% endif %}">
        <img align="right" class="profile-picture" src="{{ imageHref }}"/>
        <b>{{ item.name }}</b> <br>
        <i>{{ item.role }}</i>
        <div style="display: flex; flex-direction: column; justify-content: space-between; height: 80%;">
          <p style="width: 90%; flex:1;"><i>{{ item.blurb }}</i></p>
          {% if item.links != nil %}
          <p style="flex:1">
          {% for link in item.links %}
            <a href="{{ link[1] }}">{{ link[0]}}</a>
            {% if forloop.last %}{% else %}|{% endif %}
          {% endfor %}
          </p>
          {% endif %}
        </div>
      </div>
    {% endif %}
  {% endfor %}
  </div>
</div>

# Alumni

<div style="display: flex; justify-content: center;">
  <div class="group-counter">
  {% for item in alumniMembers %}
    {% assign imageHref = '/images/hu/' | append: item.image | prepend: site.baseurl %}
    {% if item.current %}
      <div class="human" style="{% if forloop.last %}flex:0.47;{% else %}flex:1;{% endif %}">
        <img align="right" class="profile-picture" src="{{ imageHref }}"/>
        <b>{{ item.name }}</b> <br>
        <i>{{ item.role }}</i>
        <div style="display: flex; flex-direction: column; justify-content: space-between; height: 80%;">
          <p style="width: 95%; flex:1;"><i>{{ item.blurb }}</i></p>
          {% if item.links != nil %}
          <p style="flex:1">
          {% for link in item.links %}
            <a href="{{ link[1] }}">{{ link[0]}}</a>
            {% if forloop.last %}{% else %}|{% endif %}
          {% endfor %}
          </p>
          {% endif %}
        </div>
      </div>
    {% endif %}
  {% endfor %}
  </div>
</div>
