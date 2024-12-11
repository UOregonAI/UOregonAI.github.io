---
title: Graph Machine Learning Seminar Series
layout: default
meta-description: "Seminar series on the frontier of machine learning. Open to public every XXX x:xx-x:xx pm. Recordings are available to the public. "
---

<!-- <img src="/images/f2023i.png" width="100%" style="border-radius:10px"> -->

<div align="center">
    <h2>Announcements</h2>
</div>


<div class="announcement-group" markdown="1">
   * Our talks are open to the public. No registration is required.
   * Our virtual (Zoom) talks are on xx at xx:xx PM CT and typically last for 1 hour (approximately 45 to 50-minute talk plus Q&A).
   * Join our [Google group](xxxx) for discussions and notifications of upcoming talks. 
<!--    * Visit this site at the scheduled time to attend. If you are not affiliated with Vanderbilt, request your access [here](https://forms.gle/zijM9mau411Sx5M78). -->
</div>

{% for category in site.data.talks %}

<div align="center">
    <h2>{{ category.type }}</h2>
</div>





<div class="talk-list">
  {% for talk in category.members %}
    {% if category.type == "Happening"%}
      <div class="talk current-talk-group"> 
        <div class="current-talk-join-button"><button class="button1" role="button" type="submit" onclick="location.href='https://vanderbilt.zoom.us/j/94680589561'">Join Now</button></div>
        <div class='talk-today'>March 25, 2024 at 12:15 PM Central Time</div>
        <div class="talk-presenter">{{ talk.speaker }}</div>
        
        {% if talk.title %}
          <span>{{ talk.title }}</span>
        {% endif %}
          {% if talk.abstract %}
            <details>
              <summary>Abstract</summary>
              {{ talk.abstract }}
              {% if talk.bio %}
                <br><br>
                <strong>Bio: </strong> {{ talk.bio }}
              {% endif %}
            </details>
          {% endif %}
      </div>
    {% else %}
      <div class="talk list-group-item">
      <div class="talk-date">{{ talk.date }}</div>
      <div class="talk-presenter">{{ talk.speaker }}</div>
      {% if talk.title %}
        <div> 
          {% if talk.recording %}
            <span><a class="talk-title-link" href="{{ talk.recording }}">{{ talk.title }} <i class="bi bi-box-arrow-up-right"></i></a></span>
          {% elsif talk.livestream %}
            <span><a class="talk-title-link" href="{{ talk.livestream }}">{{ talk.title }} <i class="bi bi-box-arrow-up-right"></i></a></span>
          {% else %}
            <span>{{ talk.title }}</span>
          {% endif %}
        </div>
      {% endif %}
      
      {% if talk.abstract %}
        <details>
        <summary>Abstract</summary>
        {{ talk.abstract }}

        {% if talk.bio %}
        <br><br>
        <strong>Bio: </strong> {{ talk.bio }}
        {% endif %}

        {% if talk.recording %}
          <br><br>
          <strong><a href="{{ talk.recording }}">Video Link</a></strong>
        {% elsif talk.livestream %}
          <br><br>
          <strong><a href="{{ talk.livestream }}">Livestream Link</a></strong>
        {% endif %}
        </details>
      {% endif %}
      </div>
    {% endif %}
  {% endfor %}
  
</div>
{% endfor %}



