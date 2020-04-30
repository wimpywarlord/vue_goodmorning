<template>
  <div id="app">
    <div class="toggleWrapper">
      <input @click="changeTheme" type="checkbox" class="dn" id="dn" />
      <label for="dn" class="toggle">
        <span class="toggle__handler">
          <span class="crater crater--1"></span>
          <span class="crater crater--2"></span>
          <span class="crater crater--3"></span>
        </span>
        <span class="star star--1"></span>
        <span class="star star--2"></span>
        <span class="star star--3"></span>
        <span class="star star--4"></span>
        <span class="star star--5"></span>
        <span class="star star--6"></span>
      </label>
    </div>
    <div class="center" :class="{dark : dark_mode , girl : !dark_mode }">
      <div
        @click="sendMessage"
        class="button center"
        :class="{button_dark : dark_mode , button_girl : !dark_mode }"
      >SEND</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      dark_mode: true
    };
  },
  methods: {
    changeTheme: function() {
      console.log(this.dark_mode);
      this.dark_mode = !this.dark_mode;
      return this.dark_mode;
    },
    sendMessage: function() {
      return null;
    }
  }
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Anton&display=swap");
*,
div,
body {
  font-family: "Anton", sans-serif;
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}
body {
  width: 100vw;
}
div {
  /* border: 2px solid red; */
}
.button {
  height: 10rem;
  width: 10rem;

  border-radius: 50%;
  /* border: 2px solid red; */
}
.button_girl {
  background-color: #485460;
  color: #f1f2f6;
  font-size: 2rem;
  box-shadow: 3px 3px rgba(47, 53, 66, 0.4), 6px 6px rgba(47, 53, 66, 0.3),
    9px 9px rgba(47, 53, 66, 0.2), 12px 12px rgba(47, 53, 66, 0.1),
    15px 15px rgba(47, 53, 66, 0.05);
}
.button_dark {
  background-color: #ced6e0;
  color: #2f3542;
  font-size: 2rem;
  box-shadow: 3px 3px rgba(255, 255, 255, 0.4), 6px 6px rgba(255, 255, 255, 0.3),
    9px 9px rgba(255, 255, 255, 0.2), 12px 12px rgba(255, 255, 255, 0.1),
    15px 15px rgba(255, 255, 255, 0.05);
}
.button:hover {
  animation-name: raise;
  animation-duration: 1s;
}

@keyframes raise {
  to {
    transform: scale(1.04);
  }
}
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}
.dark {
  background-color: #747d8c;
  height: 100vh;
}
.girl {
  background-color: #f1f2f6;
  height: 100vh;
}

.toggleWrapper {
  position: absolute;
  top: 8%;
  left: 50%;
  overflow: hidden;
  padding: 0 100px;
  transform: translate3d(-50%, -50%, 0);
}
.toggleWrapper input {
  position: absolute;
  left: -99em;
}

.toggle {
  cursor: pointer;
  display: inline-block;
  position: relative;
  width: 90px;
  height: 50px;
  background-color: #83d8ff;
  border-radius: 84px;
  transition: background-color 200ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
.toggle:before {
  content: "AM";
  position: absolute;
  left: -50px;
  top: 15px;
  font-size: 18px;
}
.toggle:after {
  content: "PM";
  position: absolute;
  right: -48px;
  top: 15px;
  font-size: 18px;
  color: #749ed7;
}

.toggle__handler {
  display: inline-block;
  position: relative;
  z-index: 1;
  top: 3px;
  left: 3px;
  width: 44px;
  height: 44px;
  background-color: #ffcf96;
  border-radius: 50px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
  transition: all 400ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
  transform: rotate(-45deg);
}
.toggle__handler .crater {
  position: absolute;
  background-color: #e8cda5;
  opacity: 0;
  transition: opacity 200ms ease-in-out;
  border-radius: 100%;
}
.toggle__handler .crater--1 {
  top: 18px;
  left: 10px;
  width: 4px;
  height: 4px;
}
.toggle__handler .crater--2 {
  top: 28px;
  left: 22px;
  width: 6px;
  height: 6px;
}
.toggle__handler .crater--3 {
  top: 10px;
  left: 25px;
  width: 8px;
  height: 8px;
}

.star {
  position: absolute;
  background-color: #ffffff;
  transition: all 300ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
  border-radius: 50%;
}

.star--1 {
  top: 10px;
  left: 35px;
  z-index: 0;
  width: 30px;
  height: 3px;
}

.star--2 {
  top: 18px;
  left: 28px;
  z-index: 1;
  width: 30px;
  height: 3px;
}

.star--3 {
  top: 27px;
  left: 40px;
  z-index: 0;
  width: 30px;
  height: 3px;
}

.star--4,
.star--5,
.star--6 {
  opacity: 0;
  transition: all 300ms 0 cubic-bezier(0.445, 0.05, 0.55, 0.95);
}

.star--4 {
  top: 16px;
  left: 11px;
  z-index: 0;
  width: 2px;
  height: 2px;
  transform: translate3d(3px, 0, 0);
}

.star--5 {
  top: 32px;
  left: 17px;
  z-index: 0;
  width: 3px;
  height: 3px;
  transform: translate3d(3px, 0, 0);
}

.star--6 {
  top: 36px;
  left: 28px;
  z-index: 0;
  width: 2px;
  height: 2px;
  transform: translate3d(3px, 0, 0);
}

input:checked + .toggle {
  background-color: #749dd6;
}
input:checked + .toggle:before {
  color: #749ed7;
}
input:checked + .toggle:after {
  color: #ffffff;
}
input:checked + .toggle .toggle__handler {
  background-color: #ffe5b5;
  transform: translate3d(40px, 0, 0) rotate(0);
}
input:checked + .toggle .toggle__handler .crater {
  opacity: 1;
}
input:checked + .toggle .star--1 {
  width: 2px;
  height: 2px;
}
input:checked + .toggle .star--2 {
  width: 4px;
  height: 4px;
  transform: translate3d(-5px, 0, 0);
}
input:checked + .toggle .star--3 {
  width: 2px;
  height: 2px;
  transform: translate3d(-7px, 0, 0);
}
input:checked + .toggle .star--4,
input:checked + .toggle .star--5,
input:checked + .toggle .star--6 {
  opacity: 1;
  transform: translate3d(0, 0, 0);
}
input:checked + .toggle .star--4 {
  transition: all 300ms 200ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
input:checked + .toggle .star--5 {
  transition: all 300ms 300ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
input:checked + .toggle .star--6 {
  transition: all 300ms 400ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
}
</style>
