---
# Files in this folder represent a Widget Page (homepage)
type: widget_page

# Homepage is headless, other widget pages are not.
---
{{ $sitetags := .Site.Taxonomies.tags }}
{{ $tagshalf := int (div (len $sitetags) 2) }}
{{ $.Scratch.Set "firsthalf" 0 }}
{{ $.Scratch.Set "secondhalf" 0 }}
<ul>
	{{ range $name, $taxonomy := $sitetags }}
		{{ $.Scratch.Add "firsthalf" 1}}
		{{ if le ($.Scratch.Get "firsthalf") $tagshalf }}
		<li><a href="/tags/{{$name | urlize}}">{{ $name }} ({{ $taxonomy.Count }})</a></li>
		{{ end }}
	{{ end }}
</ul>
<ul>
	{{ range $name, $taxonomy := $sitetags }}
		{{ $.Scratch.Add "secondhalf" 1}}
		{{ if gt ($.Scratch.Get "secondhalf") $tagshalf }}
		<li><a href="/tags/{{$name | urlize}}">{{ $name }} ({{ $taxonomy.Count }})</a></li>
		{{ end }}
	{{ end }}		
</ul>
https://discourse.gohugo.io/t/how-can-i-separate-list-of-tags-into-2-columns/8034