<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">{{ quote }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quote: String
  }
};
</script>

<style>
.panel {
  margin-top: 20px;
}

.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 30px;
  color: #6e6e6e;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>