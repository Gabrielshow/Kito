<template>
  <a href="#" class="neon-button">Kito</a>
</template>

<style scoped>
.neon-button {
  font-size: 4rem;
  display: inline-block;
  cursor: pointer;
  text-decoration: none;
  color: var(--clr-neon);
  border: var(--clr-neon) 0.125em solid;
  padding: 0.25em 1em;
  border-radius: 0.25em;
  text-shadow:
    0 0 0.125em hsl(0 0% 100% / 0.3),
    0 0 0.45em currentColor;

  box-shadow:
    inset 0 0 0.5em 0 var(--clr-neon),
    0 0 0.5em 0 var(--clr-neon);
  position: relative;
}

.neon-button::before {
  pointer-events: none;
  content: '';
  position: absolute;
  background: var(--clr-neon);
  top: 120%;
  left: 0;
  height: 100%;
  width: 100%;

  transform: perspective(1em) rotateX(40deg) scale(1, 0.35);
  filter: blur(1.2em);
  opacity: 0.7;
}

.neon-button::after {
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  box-shadow: 0 0 2em 0.5em var(--clr-neon);
  opacity: 0;
  background-color: var(--clr-neon);
  z-index: -1;
  transition: opacity 100ms linear;
}

.neon-button:hover,
.neon-button:focus {
  color: var(--clr-bg);
  text-shadow: none;
}

.neon-button:hover::before,
-neon-button:focus::before {
  opacity: 1;
}

.neon-button:hover::after,
.neon-button:focus::after {
  opacity: 1;
}
</style>
<script setup></script>
