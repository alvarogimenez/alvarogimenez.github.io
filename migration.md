```
<h2>(.*)</h2>             -> \n## $1
(<a .*aligncenter.*</a>)  -> <div style="text-align: center">$1</div>
class=".*alignleft[^"]*"  -> align="left"
class="[^"]+"             -> [EMPTY]
```