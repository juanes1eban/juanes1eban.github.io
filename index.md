---
layout: default
title: "Curriculum Vitae"
description: "Ingeniero Civil en Computacion con +15 anos de experiencia en desarrollo full-stack"
---

<section id="about">
    <h2>Acerca de Mi</h2>
    <p class="about-text" itemprop="description">
        {{ site.data.personal.bio }}
    </p>
    <p style="margin-top: 15px; font-style: italic; color: #666;">"{{ site.data.personal.quote }}"</p>
</section>

<section id="experience">
    <h2>Experiencia Laboral</h2>
    {% for experience in site.data.experiences %}
        {% include experience-card.html experience=experience %}
    {% endfor %}
</section>

<section id="skills">
    <h2>Conocimientos y Aptitudes</h2>
    <div class="skills-grid">
        {% for category in site.data.skills.categories %}
            {% include skill-category.html category=category %}
        {% endfor %}
    </div>
</section>

<section id="projects">
    <h2>Proyectos Destacados - Contribuciones Git (SAG)</h2>
    <p class="section-intro">Repositorios con commits confirmados bajo el email <code>juan.valenzuelar@sag.gob.cl</code>. Total: ~1,948 commits en 8 repositorios.</p>
    
    <div class="skills-grid">
        {% for project in site.data.projects %}
            {% include project-card.html project=project %}
        {% endfor %}
    </div>
    
    <h3 style="margin-top: 25px; margin-bottom: 15px; color: var(--primary-color);">Otros Proyectos (Sin Git - Propiedad del Sistema)</h3>
    <div class="skills-grid">
        {% for project in site.data.projects.other_projects %}
        <div class="skill-category">
            <h3>{{ project.name }}</h3>
            <p style="font-size: 0.85rem; color: #666;">{{ project.description }}</p>
            <div class="skill-tags" style="margin-top: 10px;">
                {% for tech in project.tech %}
                <span class="skill-tag">{{ tech }}</span>
                {% endfor %}
            </div>
        </div>
        {% endfor %}
    </div>
</section>

<section id="education">
    <h2>Formacion Academica</h2>
    {% for edu in site.data.education %}
    <div class="education-item" {% if forloop.first %}itemprop="alumniOf" itemscope itemtype="https://schema.org/CollegeOrUniversity"{% endif %}>
        <h3 {% if forloop.first %}itemprop="name"{% endif %}>{{ edu.institution }}</h3>
        <p><strong>{{ edu.degree }}</strong></p>
        {% if edu.additional %}
        <p>{{ edu.additional }}</p>
        {% endif %}
        <p class="period">
            <time datetime="{{ edu.start_year }}">{{ edu.start_year }}</time> - 
            <time datetime="{{ edu.end_year }}">{{ edu.end_year }}</time> | {{ edu.location }}
        </p>
    </div>
    {% endfor %}
</section>

<section id="certifications">
    <h2>Certificaciones y Cursos</h2>
    {% for cert in site.data.certifications %}
    <div class="cert-item">
        <h4>{{ cert.name }}</h4>
        <p>{{ cert.provider }}{% if cert.instructor %} - {{ cert.instructor }}{% endif %}{% if cert.instructors %} - {{ cert.instructors | join: ' y ' }}{% endif %}</p>
        {% if cert.type %}<p>{{ cert.type }}</p>{% endif %}
        {% if cert.credential %}<p>{{ cert.credential }}</p>{% endif %}
        {% if cert.date %}<p>Expedicion: {{ cert.date }}</p>{% endif %}
    </div>
    {% endfor %}
</section>

<section id="languages">
    <h2>Idiomas</h2>
    <ul>
        {% for lang in site.data.personal.languages %}
        <li><strong>{{ lang.name }}:</strong> {{ lang.level }}</li>
        {% endfor %}
    </ul>
</section>

<section id="volunteering">
    <h2>Voluntariado</h2>
    {% for vol in site.data.volunteering %}
    <div class="experience-item">
        <h3>{{ vol.role }}</h3>
        <p class="company">{{ vol.organization }}</p>
        <p class="period">
            <time datetime="{{ vol.start_date }}">
                {% assign start = vol.start_date | split: '-' %}
                {% case start[1] %}
                    {% when '01' %}Enero
                    {% when '02' %}Febrero
                    {% when '03' %}Marzo
                    {% when '04' %}Abril
                    {% when '05' %}Mayo
                    {% when '06' %}Junio
                    {% when '07' %}Julio
                    {% when '08' %}Agosto
                    {% when '09' %}Septiembre
                    {% when '10' %}Octubre
                    {% when '11' %}Noviembre
                    {% when '12' %}Diciembre
                {% endcase %} {{ start[0] }}
            </time> - 
            <time datetime="{{ vol.end_date }}">
                {% assign end = vol.end_date | split: '-' %}
                {% case end[1] %}
                    {% when '01' %}Enero
                    {% when '02' %}Febrero
                    {% when '03' %}Marzo
                    {% when '04' %}Abril
                    {% when '05' %}Mayo
                    {% when '06' %}Junio
                    {% when '07' %}Julio
                    {% when '08' %}Agosto
                    {% when '09' %}Septiembre
                    {% when '10' %}Octubre
                    {% when '11' %}Noviembre
                    {% when '12' %}Diciembre
                {% endcase %} {{ end[0] }}
            </time>
        </p>
        <p>{{ vol.description }}</p>
    </div>
    {% endfor %}
</section>

<section id="references">
    <h2>Referencias Profesionales</h2>
    <div class="references-grid">
        {% for ref in site.data.references %}
        <div class="reference-card">
            <h4>{{ ref.name }}</h4>
            <p class="position">{{ ref.position }}</p>
            {% if ref.title %}<p>{{ ref.title }}</p>{% endif %}
            <p>{{ ref.phone }}{% if ref.email %} | {{ ref.email }}{% endif %}</p>
        </div>
        {% endfor %}
    </div>
</section>

<section id="availability">
    <h2>Disponibilidad</h2>
    <p><strong>Estado actual:</strong> {{ site.data.personal.availability.status }}</p>
    <p><strong>Cargos de interes:</strong> {{ site.data.personal.availability.roles | join: ', ' }}</p>
    <p><strong>Modalidad:</strong> {{ site.data.personal.availability.modality }}</p>
    <p><strong>Contactos en LinkedIn:</strong> {{ site.data.personal.availability.linkedin_connections }}</p>
</section>
