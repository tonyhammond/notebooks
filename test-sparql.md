
## test-sparql.ipynb

This is a very basic SPARQL notebook example. For more worked examples see the [sparql-kernel](https://github.com/paulovn/sparql-kernel/tree/master/examples) project.

#### Magics

So let's first list out the magics as a useful reference.


```sparql
%lsmagics
```


<div class="krn-spql"><div class="magic-help">Available magics:<br/>%auth  %display  %endpoint  %format  %graph  %lang  %log  %lsmagics  %outfile  %prefix  %qparam  %show<br/><br/>%auth (basic|digest|none) &lt;username&gt; &lt;passwd&gt; : send HTTP authentication<br/>%display raw | table [withtypes] | diagram [svg|png] [withliterals] : set display format<br/>%endpoint &lt;url&gt; : set SPARQL endpoint. **REQUIRED**<br/>%format JSON | N3 | XML | any | default : set requested result format<br/>%graph &lt;uri&gt; : set default graph for the queries<br/>%lang &lt;lang&gt; [...] | default | all : language(s) preferred for labels<br/>%log critical | error | warning | info | debug : set logging level<br/>%lsmagics  : list all magics<br/>%outfile &lt;filename&gt; | NONE : save raw output to a file (use &quot;%d&quot; in name to add cell number, &quot;NONE&quot; to cancel saving)<br/>%prefix &lt;name&gt; [&lt;uri&gt;] : set (or delete) a persistent URI prefix for all queries<br/>%qparam &lt;name&gt; [&lt;value&gt;] : add (or delete) a persistent custom parameter to the endpoint query<br/>%show &lt;n&gt; | all : maximum number of shown results</div></div>


#### Endpoint

Next we'll set the SPARQL endpoint we're going to query – here DBpedia.


```sparql
%endpoint http://dbpedia.org/sparql
```


<div class="krn-spql"><div class="magic">Endpoint set to: http://dbpedia.org/sparql</div></div>


#### Format

Then let's specify a no frills output table format.


```sparql
%display table
```


<div class="krn-spql"><div class="magic">Display: table</div></div>


#### Query

And then the SPARQL query itself. This just lists an arbitrary page of musicians with their gender. Will look for a more inspired example later.


```sparql
select distinct ?artist ?gender
where {
   ?s a yago:Musician110339966 .
   optional { ?s foaf:gender ?gender }
   bind (?s as ?artist)
}
limit 100 offset 60
```


<div class="krn-spql"><table><tr class=hdr><th>artist</th>
<th>gender</th></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Gary_Numan" target="_other">http://dbpedia.org/resource/Gary_Numan</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/George_Michael" target="_other">http://dbpedia.org/resource/George_Michael</a></td>
<td class=val>male</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Georges-Eugène_Haussmann" target="_other">http://dbpedia.org/resource/Georges-Eugène_Haussmann</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Gillian_Anderson" target="_other">http://dbpedia.org/resource/Gillian_Anderson</a></td>
<td class=val>female</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Giovanni_Battista_Pergolesi" target="_other">http://dbpedia.org/resource/Giovanni_Battista_Pergolesi</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Giovanni_Pacini" target="_other">http://dbpedia.org/resource/Giovanni_Pacini</a></td>
<td class=val>male</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Giovanni_Paisiello" target="_other">http://dbpedia.org/resource/Giovanni_Paisiello</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Glenn_Close" target="_other">http://dbpedia.org/resource/Glenn_Close</a></td>
<td class=val>female</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Glenn_Hughes" target="_other">http://dbpedia.org/resource/Glenn_Hughes</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Goldie" target="_other">http://dbpedia.org/resource/Goldie</a></td>
<td class=val>male</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Goldie_Hawn" target="_other">http://dbpedia.org/resource/Goldie_Hawn</a></td>
<td class=val>female</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Gustav_Holst" target="_other">http://dbpedia.org/resource/Gustav_Holst</a></td>
<td class=val>male</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Gwen_Verdon" target="_other">http://dbpedia.org/resource/Gwen_Verdon</a></td>
<td class=val>female</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Gwyneth_Paltrow" target="_other">http://dbpedia.org/resource/Gwyneth_Paltrow</a></td>
<td class=val>female</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Hector_Berlioz" target="_other">http://dbpedia.org/resource/Hector_Berlioz</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Henry_Mancini" target="_other">http://dbpedia.org/resource/Henry_Mancini</a></td>
<td class=val>male</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Herbie_Hancock" target="_other">http://dbpedia.org/resource/Herbie_Hancock</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Hildegard_Knef" target="_other">http://dbpedia.org/resource/Hildegard_Knef</a></td>
<td class=val>female</td></tr><tr class=odd><td class=val><a href="http://dbpedia.org/resource/Ian_Curtis" target="_other">http://dbpedia.org/resource/Ian_Curtis</a></td>
<td class=val>male</td></tr><tr class=even><td class=val><a href="http://dbpedia.org/resource/Ian_Dury" target="_other">http://dbpedia.org/resource/Ian_Dury</a></td>
<td class=val>male</td></tr></table><div class="tinfo">Total: 100, Shown: 20</div></div>

