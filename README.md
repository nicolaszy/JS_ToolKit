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
Data Structures:



