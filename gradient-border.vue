<template>
  <div class="gradient-border">
    <div class="container">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  props: {
    width: {
      type: String,
      default: '100px'
    },
    height: {
      type: String,
      default: '100px'
    },
    borderRadius: {
      type: String,
      default: '8px'
    },
    gradientPadding: {
      type: String,
      default: '4px'
    },
    containerBg: {
      type: String,
      default: '#000'
    }
  }
}
</script>

<style scoped>
    .gradient-border {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      width: 100px;
      height: 100px;
      padding: 4px;
      border-radius: 8px;
    }
    .gradient-border::after {
      content: '';
      position: absolute;
      width: 150%;
      height: 150%;
      left: 50%;
      top: 50%;
      right: 0;
      bottom: 0;
      margin-top: -75%;
      margin-left: -75%;
      background: linear-gradient(to right, transparent, white, transparent);
      animation: rotate 8s linear infinite;
      filter: brightness(200%);
    }
    .container {
      width: 100%;
      height: 100%;
      border-radius: 8px;
      background: #000;
      z-index: 99;
    }
    @keyframes rotate {
      0% {
          transform: rotate(0deg);
      }
      100% {
          transform: rotate(360deg);
      }
    }
</style>
