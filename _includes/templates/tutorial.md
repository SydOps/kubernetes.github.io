* TOC
{: toc}

{% if page.concept_rankings %}{% else %}
{% include templates/_errorthrower.md missing_block='concept_rankings' tagsblock='true' purpose='provides a list of associated concepts that pertain to this topic.' tagname='concept' tieroneexample='pod' tiertwoexample='container'%}
{% endif %}

{% if overview %}

{{ overview }}

{% else %}

{% include templates/_errorthrower.md missing_block='overview' purpose='states, in one or two sentences, the purpose of this document' %}

{% endif %}


{% if objectives %}

### Objectives

{{ objectives }}

{% else %}

{% include templates/_errorthrower.md missing_block='objectives' heading='Objectives' purpose='lists the objectives for this tutorial.' %}

{% endif %}


{% if costs %}

### Costs

{{ costs }}

{% endif %}


{% if prerequisites %}

### Before you begin

{{ prerequisites }}

{% else %}

{% include templates/_errorthrower.md missing_block='prerequisites' heading='Before you begin' purpose='lists action prerequisites and knowledge prerequisites' %}

{% endif %}


{% if lessoncontent %}

### H3 Heading

Lesson content

{{ steps }}

{% else %}

{% include templates/_errorthrower.md missing_block='lessoncontent' purpose='provides the lesson content for this tutorial.' %}

{% endif %}


{% if cleanup %}

### Cleaning up

{{ cleanup }}

{% endif %}


{% if whats_next %}

### What's next

{{ whats_next }}

{% endif %}

<script language="JavaScript">
$( document ).ready(function() {
  // When the document loads, get the metadata JSON, and kick off tbl render
  $.get("/metadata.txt", function(data, status) {
    metadata = $.parseJSON(data);
    mainLogic();
  });
});
function mainLogic()
{
  topicsFilter("concept","pod","coretopics",1);
  topicsFilter("concept","pod","advancedtopics",2);
  showTags();
}
</script>
{% include tagfooter.md %}