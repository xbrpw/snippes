---
title: Hide an element for 24 hours with localStorage query
description: how to Hide an element for 24 hours with localStorage. query JS & CSS
date: 2023-08-15
tags: localStorage 
      snippe
---
Como hacer un elemento disponible, cada 24hrs. 

<!-- {% image "./possum.png", "A possum parent and two possum kids hanging from the iconic red balloon" %} -->

## Section Header

Usos como, promocion. 

Primero utilizamos su CSS

### CSS

```
.popUp {
  background-color: white;
  max-width: 20rem;
  padding: 2rem;
  margin: 0 auto;
}
```

.popUp.hidden {
  display: none;
}

### HTML

Así lo llamamos

```
<div class="popUp">
	<h1>Nos vémos en 24 horas!</h1>
	<button class="popUp-close">Bye!</button>
</div>
```


### JS

Lo más importante el JS

```
const popUp = document.querySelector('.popUp');
  const popUpCloseButton = document.querySelector('.popUp-close');
  let currentTime = new Date().getTime();

  popUpCloseButton.onclick = function () {
    popUp.classList.add('hidden');
    localStorage.setItem('popUpHidden', true);
    localStorage.setItem('timeClosed', currentTime);
  };

  if(localStorage.getItem('popUpHidden', true)) {
    popUp.classList.add('hidden');
  }

  const closedTime = parseInt(localStorage.getItem('timeClosed'));
  const oneDay = 86400000; //24hrs in ms

  if(currentTime >= closedTime + oneDay) {
    localStorage.setItem('popUpHidden', false);
    popUp.classList.remove('hidden');
  }
  ```

Nos vémos en 24 horas!
Bye!


  ### Ejemplos

<a href="/blog/firstpost/">First post</a><br>
<a href="/blog/thirdpost/">Third post</a><br>