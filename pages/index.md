---
layout: home
permalink: /
---

## Find a Research Software Engineer


<form action="{{ site.baseurl }}/" method="get">
    <input type="search" name="q" id="search-input" placeholder="Find an RSE?" style="margin-top:5px" autofocus>
    <input type="submit" value="Search" style="display: none;">
</form>

<p><span id="search-process">Loading</span> results <span id="search-query-container" style="display: none;">for "<strong id="search-query"></strong>"</span></p>
<ul id="search-results"></ul>

<script src="{{ site.baseurl }}/assets/js/lunr.min.js"></script>
<script src="{{ site.baseurl }}/assets/vendor/jquery/jquery.min.js" ></script>
<script>
(function() {
window.data = {}

$.getJSON("https://api.github.com/orgs/{{ site.github_username }}/repos", {
  format: "json"
}).done(function(data) {
  console.log("Found repos starting with {{ site.prefix }}:")
  $.each(data, function(key, value) {
    if (value.name.startsWith("{{ site.prefix }}")) {
      console.log(value.name);
      var dataurl = "{{ site.domain }}/" + value.name + '/data.json'
      console.log(dataurl)
      $.getJSON(dataurl, {
         format: "json"
       }).done(function(pages, status) {
       if (status == "success") {
         $.each(pages, function(key, value) {
             window.data[key] = value;           
         });
        }
     });
    }
  })
});

  function loadSearch() {
    console.log(window.data)
    var fileref = document.createElement('script')
    fileref.setAttribute("type","text/javascript")
    fileref.setAttribute("src", "{{ site.baseurl }}/assets/js/search.js")
    document.getElementsByTagName("head")[0].appendChild(fileref)
  }
  setTimeout(loadSearch, 1000);
})();


</script>
