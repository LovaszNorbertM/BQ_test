

<script>
import { defineComponent } from "vue";
import cover from "../../public/assets/img/bq-logo-black-quodrum-main.svg";
export default defineComponent({
  name: "WebBQCoverImage",
  components: { cover },

  data() {
    return {
      coverSrc: cover,
    };
  },

  mounted() {},

  methods: {},
});
</script>
<template>
  <span>
    <cover class="cover" />
    <div>
      <!-- <h1>Black Quodrum</h1> -->
    </div>
  </span>
</template>

<style scoped>
span {
  height: 100vh;
  width: 100vw;
  position: relative;
  display: block;
  background-color: black;
}

span .cover {
  height: 100vh;
  width: 100vw;
  /* filter: blur(2px); */
  object-fit: contain;
  position: relative;
  stroke-dasharray: 600;
  animation: dash 5s ease-in reverse infinite;
}
span .cover #tree {
  fill: rgb(0, 0, 0);
}

span::before {
  content: "";
  position: absolute;
  top: -180%;
  left: -210%;
  width: 200%;
  height: 300%;
  opacity: 0;
  transform: rotate(27deg);

  background: rgba(255, 255, 255, 0.003);
  background: linear-gradient(
    to right,
    rgba(255, 255, 255, 1) 0%,
    rgba(255, 255, 255, 1) 15%,
    rgba(255, 255, 255, 0.13) 35%,
    rgba(255, 255, 255, 0.13) 77%,
    rgba(255, 255, 255, 1) 80%,
    rgba(255, 255, 255, 0.08) 100%
  );
}
span:hover::before {
  opacity: 0.25;
  top: -30%;
  left: -10%;
  transition-property: left, top, opacity;
  transition-duration: 3s, 3s, 0.15s;
  transition-timing-function: ease;
}

span::after {
  position: absolute;
  display: block;
  content: "";
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
span div {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  width: 100%;
  height: 100%;
  top: 0;

  color: black;
  text-align: center;
  z-index: 3;
}
span div h1 {
  font-size: 5rem;
}

@keyframes dash {
  0% {
    stroke-dashoffset: 0;
  }
  50% {
    stroke-dashoffset: 1000;
  }
  100% {
    stroke-dashoffset: 0;
  }
}
</style>
