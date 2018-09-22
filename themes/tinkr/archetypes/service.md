+++
date = {{ .Date }}
publishdate = {{ .Date }}

title = "{{ replace .Name "-" " " | title }}"
tags = []

type = "service"
menu = "service"

[amp]
    elements = []
    
[service]
    lead = ""
    category = ""
    related = []
    icon = ""

[sitemap]
  changefreq = "monthly"
  priority = 0.5
  filename = "sitemap.xml"

+++
