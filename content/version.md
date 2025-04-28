+++
date = '2025-04-27'
title = 'Versions'
sidebar = false
authorbox = false
+++

<pre>
{{< build.inline >}}
Build on: {{ time.Now }}
{{ .Page.GitInfo | jsonify (dict "indent" "  ") }}
{{< /build.inline >}}