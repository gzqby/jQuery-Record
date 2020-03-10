# jQuery-Record
1.DomEval：script能通过text传递code给浏览器，之前没留意过的东西。  
```
var script = document.createElement("script");
script.text = "console.log(document.querySelector('#root'));document.querySelector('#root').innerHTML='hello wolrd'";
document.head.appendChild(script).parentNode.removeChild(script);
```
