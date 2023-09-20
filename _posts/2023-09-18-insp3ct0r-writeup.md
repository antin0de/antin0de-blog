---
layout: post
title:  "Insp3ct0r write-up"
date:   2023-09-18 15:20:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are given a website to inspect through, right clicking on the site and choose "View Sources" reveals the first part of the flag.

```html
<!-- omit... -->
	  JS (JavaScript)
	</p>
	<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
      </div>
      
    </div>
    
  </body>
</html>
```

Then on top of the file, we see references to `mycss.css` and `myjs.js`, opening `.css` file reveals the second part.

```css
/* omit... */

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```

Opening `.js` file reveals the last part.

```js
// omit...

window.onload = function() {
    openTab('tabintro', this, '#222');
}

/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?f10be399} */
```

Our flag is: `picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?f10be399}`