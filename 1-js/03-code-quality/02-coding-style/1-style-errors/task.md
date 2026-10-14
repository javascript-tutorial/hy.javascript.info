importance: 4

---

# Վատ ոճ

Ի՞նչ սխալ կա ստորև բերված կոդի ոճում։

```js no-beautify
function pow(x,n)
{
  let result=1;
  for(let i=0;i<n;i++) {result*=x;}
  return result;
}

let x=prompt("x?",''), n=prompt("n?",'')
if (n<=0)
{
  alert(`Power ${n} is not supported, please enter an integer number greater than zero`);
}
else
{
  alert(pow(x,n))
}
```

Ուղղեք այն։
