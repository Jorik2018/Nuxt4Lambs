<template>
  <div id='webviewer' ref='viewer'></div>
</template>

<script>
export default {
  name: 'WebViewer',
  props: {
    path: String,
    url: String
  },
  mounted: function () {
    import('@pdftron/webviewer').then(() => {

        WebViewer({
            path: '../webviewer',
            initialDoc: this.url, // replace with your own PDF file
          }, this.$refs.viewer).then((instance) => {
            // call apis here
          });
    })
  }
}
</script>

<style>
#webviewer {
  height: 100vh;
}
</style>