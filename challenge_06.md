## Challenge 6
### Why we rebase: What Git lacks in semantics

Consider this pseudo code:

dog.code
```
├─0 class dog {
├─1   string name
├─2   string breed
├─3
├─4   function introduce() {
├─5     print "Hello, my name is %s", name
├─6   }
└─7 }
```

main.code
```
├─0 import dog
├─1
├─2 function main() {
├─3
└─4 }
```
