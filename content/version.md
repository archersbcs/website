+++
date = '2025-04-27'
title = 'Version'
sidebar = false
authorbox = false
+++

{{< build.inline >}}
{{ $keys := slice "abbreviatedHash" "commitDate" }}

<!-- Hack - GitInfo to json to dict -->
{{ $j := .Page.GitInfo | jsonify (dict "indent" "  ") }}
{{ $gitinfo :=  unmarshal $j }}
<!-- /Hack -->

<table>
    <tr>
        <td>build</td>
        <td>{{- time.Now }}</td>
    </tr>
    {{- range $k := $keys }}
    <tr>
        <td>{{- $k }}</td>
        <td>{{- index $gitinfo $k }}</td>
    </tr>
    {{- end }}
</table>
{{< /build.inline >}}
