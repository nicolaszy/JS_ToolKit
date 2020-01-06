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
Arrays können wie alle JS Objekte um weitere Funktionen erweitert werden. Beispiel: </br>
<code>Array.prototype.eq = function(ys){ </code></br>
            <code>if(this.length != ys.length){
                return false; 
            }</code></br>
            <code>let equals = true;</code></br>
            <code>this.forEach( (x, index) => {
            </code></br>
            <code>if(x!==ys[index]){
                equals = false;
            }
            })</code></br>
            <code>return equals;</code></br>
         <code>}</code></br>
</br>
</br>
JS Scopes: </br>
<code>x = … -> mutable, global scope (in scope after first use) </code></br>
<code>var x = … -> mutable, “hoisted” scope (egal wo das var hingeschrieben wird, es wird so behandelt als wäre es am Anfang der Fkt. hingeschrieben worden, aber Scope is Funktion!) </code></br>
<code>let x = …. -> mutable, local scope </code></br>
<code>const x = … -> immutable, local scope </code></br>
</code> </br>
</br>
Functions: </br>
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
Für den Fall dass die Liste leer ist kann auch ein Startwert mitgegeben werden: </br>
<code> [1,2,3].reduce(addCurrentToTotal,0); </code></br> 

</br>
Data Structures:</br>
<code>const pair = x => y => f => f(x)(y);</code></br>
Nun müssen wir jeweils das erste oder zweite Element aus diesem Pair rauslesen können:
<code>const fst = x => y => x;</code></br>
<code>const snd = x => y => y;</code></br>
Damit haben wir alles das wir alles das wir brauchen: </br>
pair(8)(9)(fst) selektiert das erste und pair(8)(9)(snd) das zweite Element! </br>
Um das Pair auch mit fst(pair(8)(9)) selektieren zu können, benötigen wir erneut die Identität und die konstante Fkt:
<code>const id = x => x;
const konst = x => y => x;</code></br>
Nun können wir True definieren als: </br>
<code>const T = konst;</code></br>
Und false als: </br>
<code>const F = konst(id);</code></br> 
Nun können wir fst und snd neu definieren, diese mal aber als Funktionen, die eine Fkt. entgegennehmen und damit True oder False aufrufen: </br>
<code>const fst = p => p(T);</code></br> 
<code>const snd = p => p(F);</code></br> 
Nun können wir auch fst(pair(8)(9)) aufrufen, um die Zahl 8 wieder zu erhalten. </br>


Wir können sogar weiter gehen und ein Objekt Person aus diesen Pairs erstellen: </br>
<code>const person = 
firstname =>
lastname =>
age =>
pair (pair(firstname)(lastname)) (age);</code></br>

Nun können wir wie vorher mit 


