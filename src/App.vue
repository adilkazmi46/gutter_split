<template>
  <div id="app" @mouseover="toggleGutter = true" @mouseleave="toggleGutter = false">
    <SplitGrid class="sb_split-grid" v-bind="splitGridOptions" direction="row">
      <SplitGrid  v-bind="splitGridOptions" class="sb_sub-grid">
        <SplitGridArea>
          <img
            width="100%"
            height="100%"
            src="https://cdn4.vectorstock.com/i/1000x1000/82/33/person-gray-photo-placeholder-woman-vector-24138233.jpg"
          >
        </SplitGridArea>
        <SplitGridGutter v-bind:class="{ active: toggleGutter }" :render="true"/>
        <SplitGridArea>
          <img
            width="100%"
            height="100%"
            src="https://cdn4.vectorstock.com/i/1000x1000/82/33/person-gray-photo-placeholder-woman-vector-24138233.jpg"
          >
        </SplitGridArea>
      </SplitGrid>
      <SplitGridGutter v-bind:class="{ active: toggleGutter }" :render="true"/>
      <SplitGrid  v-bind="splitGridOptions" class="sb_sub-grid">
        <SplitGridArea>
          <img
            width="100%"
            height="100%"
            src="https://cdn4.vectorstock.com/i/1000x1000/82/33/person-gray-photo-placeholder-woman-vector-24138233.jpg"
          >
        </SplitGridArea>
        <SplitGridGutter v-bind:class="{ active: toggleGutter }" :render="true"/>
        <SplitGridArea>
          <img
            width="100%"
            height="100%"
            src="https://cdn4.vectorstock.com/i/1000x1000/82/33/person-gray-photo-placeholder-woman-vector-24138233.jpg"
          >
        </SplitGridArea>
      </SplitGrid>
    </SplitGrid>
  </div>
</template>
<script>
import { SplitGrid, SplitGridArea, SplitGridGutter } from "vue-split-grid";

export default {
  name: "App",
  components: {
    SplitGrid,
    SplitGridArea,
    SplitGridGutter
  },
  data() {
    return {
      toggleGutter: false,
      splitGridOptions: {
        columnMinSizes: { 0: 0 },
        snapOffset: 0,
        dragInterval: 0,
        gutterSize: 10
      }
    };
  }
};
</script>
<style lang="scss">
body {
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  overflow: scroll;


  img {
    width: calc(100% + 10px);
    height: 100%;
    /* object-fit:cover;  */
  }
  .sb_sub-grid{
    grid-template-columns: 1fr 10px 1fr ;
  }

  .vsg_gutter {
    background-color: transparent;

  } 
  .active{
    background-color: gray !important;
  }
}

.sb_split-grid {
  height: calc(100% - 30px);
}
</style>
