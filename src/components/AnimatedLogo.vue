<template>
  <p id="p-first">personal/</p>
  <p id="p-second">universal</p>
</template>

<style scoped>
p {
  position: absolute;
  font-size: 1.5rem;
  font-weight: 600;
  rotate: -30deg;

  padding: 0.25rem 0.75rem;
  border-radius: var(--br);
  color: var(--off-brown);
}
#p-first {
  top: 3rem;
  left: 1rem;
  background: var(--purple);
  animation: bounce-in forwards 1s;
}
#p-second  {
  top: 4rem;
  left: 6rem;
  background: var(--brown);
  animation: bounce-in-second forwards 2s;
}

@media (min-width: 768px) {
  p {
    scale: 1.5;
  }
  #p-first {
    top: 4rem;
    left: 3rem
  }
  #p-second  {
    top: 5rem;
    left:12rem;
  }
}

@media (min-width: 1024px) {
  p {
    scale: 2;
  }
  #p-first {
    top: 5rem;
    left: 10rem;
  }
  #p-second  {
    top: 7rem;
    left: 20rem;
  }
}

@keyframes bounce-in {
  0% {
    opacity: 0;
    transform: translateY(-2000px);
  }
  60% {
    opacity: 1;
    transform:scaleY(0.6) translateY(30px)
  }
  100% {
    transform:  scaleY(1) translateY(0)
  }
}

@keyframes bounce-in-second {
  0% {
    opacity: 0;
  }
  50% {
    transform: translateY(-2000px);
  }
  80% {
    opacity: 1;
    transform:scaleY(0.6) translateY(30px)
  }
  100% {
    transform:  scaleY(1) translateY(0)
  }
}

</style>
