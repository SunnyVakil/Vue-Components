<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quotes"]
};
</script>

<style >
.panel-body {
  font-family: "Sacramento", cursive;
  font-size: 1.5rem;
  color: #6e6e6e;
  background: #221f1f;
  border-radius: 4px;
  text-align: center;
}

.quote {
  cursor: pointer;
}
.quote:hover {
  color: #ffe2e2;
}
</style>