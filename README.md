# BUPT-encodeInp
> A Solution of encodeInp undefined

![image](https://user-images.githubusercontent.com/56634309/156722741-cc8e1590-7378-4232-8e31-50f2f49a53ab.png)

# step 1 右键 `检查`(win) / `审查元素`(mac) 打开控制台
![image](https://user-images.githubusercontent.com/56634309/156722863-8f60f9b1-8c9f-41ce-9f72-03a22946812d.png)

# step2 复制下面的代码, 粘贴到控制台, 然后按`Enter`, 再次登入
```js
function find(p, a, c, k, e, d) {
  e = function (c) {
    return (
      (c < a ? "" : e(parseInt(c / a))) +
      ((c = c % a) > 35 ? String.fromCharCode(c + 29) : c.toString(36))
    );
  };
  if (!"".replace(/^/, String)) {
    while (c--) d[e(c)] = k[c] || e(c);
    k = [
      function (e) {
        return d[e];
      },
    ];
    e = function () {
      return "\\w+";
    };
    c = 1;
  }
  while (c--)
    if (k[c]) p = p.replace(new RegExp("\\b" + e(c) + "\\b", "g"), k[c]);
  console.log(p);
  return p;
}

find(
  'b 9="o+/=";p q(a){b e="";b 8,5,7="";b f,g,c,1="";b i=0;m{8=a.h(i++);5=a.h(i++);7=a.h(i++);f=8>>2;g=((8&3)<<4)|(5>>4);c=((5&s)<<2)|(7>>6);1=7&t;k(j(5)){c=1=l}v k(j(7)){1=l}e=e+9.d(f)+9.d(g)+9.d(c)+9.d(1);8=5=7="";f=g=c=1=""}u(i<a.n);r e}',
  32,
  32,
  [
    "",
    "enc4",
    "",
    "",
    "",
    "chr2",
    "",
    "chr3",
    "chr1",
    "keyStr",
    "input",
    "var",
    "enc3",
    "charAt",
    "output",
    "enc1",
    "enc2",
    "charCodeAt",
    "",
    "isNaN",
    "if",
    "64",
    "do",
    "length",
    "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789",
    "function",
    "encodeInp",
    "return",
    "15",
    "63",
    "while",
    "else",
  ],
  0,
  {}
);

var keyStr =
  "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/=";
function encodeInp(input) {
  var output = "";
  var chr1,
    chr2,
    chr3 = "";
  var enc1,
    enc2,
    enc3,
    enc4 = "";
  var i = 0;
  do {
    chr1 = input.charCodeAt(i++);
    chr2 = input.charCodeAt(i++);
    chr3 = input.charCodeAt(i++);
    enc1 = chr1 >> 2;
    enc2 = ((chr1 & 3) << 4) | (chr2 >> 4);
    enc3 = ((chr2 & 15) << 2) | (chr3 >> 6);
    enc4 = chr3 & 63;
    if (isNaN(chr2)) {
      enc3 = enc4 = 64;
    } else if (isNaN(chr3)) {
      enc4 = 64;
    }
    output =
      output +
      keyStr.charAt(enc1) +
      keyStr.charAt(enc2) +
      keyStr.charAt(enc3) +
      keyStr.charAt(enc4);
    chr1 = chr2 = chr3 = "";
    enc1 = enc2 = enc3 = enc4 = "";
  } while (i < input.length);
  return output;
}
```
