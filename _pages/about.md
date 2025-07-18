---
permalink: /
title: "About"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<div id="about">
I am a Ph.D. candidate in Computer Science at the University of Illinois Urbana-Champaign, advised by [Professor Tarek Abdelzaher](https://abdelzaher.cs.illinois.edu/). My research lies at the intersection of large language models (LLMs), agent-based modeling, and social simulation. Specifically, I design persona-grounded LLM agents that simulate ideological behavior, belief shifts, and community-level dynamics in response to external events such as propaganda, misinformation, and persuasive narratives.

I work closely with [Professor Dilek Hakkani-Tür](https://siebelschool.illinois.edu/about/people/faculty/dilek) and [Professor Heng Ji](https://blender.cs.illinois.edu/hengji.html), exploring research directions in natural language understanding, multimodal retrieval, and social behavior modeling.

My long-term goal is to develop computational frameworks that bridge LLMs and social science, enabling interpretable, scalable, and language-aware simulations of complex human interactions.

## Education
- **Ph.D. candidate in Computer Science**, University of Illinois Urbana-Champaign, Champaign, IL (Expected May 2027)
- **Master of Science in Data Science**, Columbia University, New York, NY (May 2022)
- **Bachelor of Engineering**, Nanjing University of Posts and Telecommunications, Nanjing, CN (July 2019)

## Work Experience
<div class="work-item">
  <img src="../images/amazon.png" alt="Amazon" class="company-logo">
  <div class="work-content">
    Applied Science Intern | Causal Inference, Persona Modeling<br/>
    Amazon Alexa AI | Summer 2025
  </div>
</div>

<div class="work-item">
  <img src="../images/bytedance.png" alt="ByteDance" class="company-logo">
  <div class="work-content">
    Data Science Intern | Data Mining, User Segmentation<br/>
    ByteDance | Summer 2022
  </div>
</div>
</div>

<style>
.work-item, .publication-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 20px;
}
.company-logo {
  width: 80px;
  height: 80px;
  margin-right: 15px;
  object-fit: contain;
  min-width: 80px;
}
.paper-icon {
  width: 40px;
  height: 40px;
  margin-right: 15px;
  object-fit: contain;
  min-width: 40px;
}
.work-content, .paper-content {
  flex: 1;
}
.paper-title {
  margin-bottom: 0.3em;
}
.paper-authors {
  margin-bottom: 0.3em;
  color: #4a4a4a;
}
.paper-venue {
  color: #666;
}
</style>

<div id="publications">
## Publications

You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.

### First-authored Publications
{% assign first_author = site.publications | where_exp:"item","item.first_author" | sort: "number" | reverse %}
{% for post in first_author %}
  <div class="publication-item">
    {% assign paper_number = post.number | downcase %}
    {% assign paper_files = site.static_files | where_exp: "file", "file.path contains '/images/papers/'" %}
    {% for file in paper_files %}
      {% assign file_number = file.name | split: '_' | first %}
      {% if file_number == paper_number %}
        <img src="../images/papers/{{ file.name }}" alt="Paper {{ post.number }}" class="paper-icon">
        {% break %}
      {% endif %}
    {% endfor %}
    <div class="paper-content">
      {{ post.content }}
    </div>
  </div>
{% endfor %}

### Co-authored Publications
{% assign co_author = site.publications | where_exp:"item","item.first_author != true" | sort: "number" | reverse %}
{% for post in co_author %}
  <div class="publication-item">
    {% assign paper_number = post.number | downcase %}
    {% assign paper_files = site.static_files | where_exp: "file", "file.path contains '/images/papers/'" %}
    {% for file in paper_files %}
      {% assign file_number = file.name | split: '_' | first %}
      {% if file_number == paper_number %}
        <img src="../images/papers/{{ file.name }}" alt="Paper {{ post.number }}" class="paper-icon">
        {% break %}
      {% endif %}
    {% endfor %}
    <div class="paper-content">
      {{ post.content }}
    </div>
  </div>
{% endfor %}
</div>
