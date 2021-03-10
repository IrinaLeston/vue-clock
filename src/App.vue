<template>
  <div class="container">
    <div class="dark-box">
      <div class="hour">{{hour}}</div>
      <div class="dots">:</div>
      <div class="min">{{min}}</div>
      <div class="dots">:</div>
      <div class="sec">{{sec}}</div>
      <div class="mode"></div>
    </div>

    <p>Creado por <strong>Irina</strong></p>
  </div>
</template>

<script>
export default {
  name: "App",
  data () {
    return {
      hour: "--",
      min: "--",
      sec: "--"
    };
  },
  methods: {
    setTime () {
      setInterval(() => {
        const date = new Date();
        this.hour = date.getHours().toString().padStart(2, "0");
        this.min = date.getMinutes().toString().padStart(2, "0");
        this.sec = date.getSeconds().toString().padStart(2, "0");
      }, 1000);
    }
  },
  mounted () {
    this.setTime();
  }

};

</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=DotGothic16&display=swap');
  strong {
  color: rgb(93, 177, 149);
}
.container {
  background: linear-gradient(to right, grey, rgb(46, 44, 44));
  display: flex;
  justify-content: center;
  align-items: center;
  width: 700px;
  height: 200px
}
.dark-box {
  width: 600px;
  height: 150px;
  background: black;
  border-radius: 20px;
  color: brown;
  font-size: 70px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'DotGothic16', sans-serif;
}
</style>
