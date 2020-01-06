# Javscript Toolkit
<br/>
Arrays:<br/>
initialisation of array w/ indices as elements: 
<code>
let x = Array.from({length: 4}, (it, idx) => idx) 
</code> 
</br>
reverse Array:
<code>
x.reverse() -> x itself is now reversed!!! </br>
</code>
</br>
neues Array mit reverse von x: 
<code>
[...x].reverse() -> spread operator [...x] dupliziert x... </br>
</code>
</br>
auch möglich: 
<code>
[...x,...x].reverse() oder [-1,...x].reverse() </br>
</code>
</br>
</br>
JS Scopes:
<code>x = … -> mutable, global scope (in scope after first use) </code></br>
<code>var x = … -> mutable, “hoisted” scope (egal wo das var hingeschrieben wird, es wird so behandelt als wäre es am Anfang der Fkt. hingeschrieben worden, aber Scope is Funktion!) </code></br>
<code>let x = …. -> mutable, local scope </code></br>
<code>const x = … -> immutable, local scope </code></br>
</code> </br>
</br>
Functions:
<code>function foo(){…}; foo() </code></br>
<code>(function foo(){…})(); </code></br>
<code>(function(){…})(); </code></br>
<code>( () => {…} )(); //most compact </code></br>
mit Function constructor: </br>
<code> const sum = new Function('a', 'b', 'return a + b');</code></br>
und dann so aufrufen:
<code> sum(5, 10); </code></br>
</br>
</br>
Lambda Kalkül: </br> 
identity: </br>
<code> const id = x => x; </code></br>
times: </br>
<code>const times = a => b => a*b; </code></br>
Aufruf: </br>
<code>const times(2)(3) </code></br>
Wichtig: times(2) gibt uns eine Funktion, die wir auch später noch mit der zweiten Zahl aufrufen können (lazy evaluation) </br>
map: Funktion auf alle Elemente eines Arrays anwenden: <br>
<code>[1,2,3].map(x => times(2)(x)) //multipliziert alle Zahlen mit 2 </code></br> 
filter: nur Elemente, welche mit Fkt. zu true evaluieren behalten: </br>
<code> const odd = x => x % 2 === 1; </code></br> 
<code> [1,2,3].filter(odd); </code></br> 
reduce: Elemente miteinander verarbeiten: </br>
<code> const addCurrentToTotal = (acc,cur) => acc+cur </code></br>
<code> [1,2,3].reduce(addCurrentToTotal); </code></br> 
</br>
Data Structures:



