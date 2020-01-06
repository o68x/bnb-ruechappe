<script>
  import 'wired-elements';
</script>

<style>
  wired-card {
  }
</style>

<wired-card>
  <h3><slot name="title"></slot></h3><br />
  <p><slot name="body"></slot></p>
</wired-card>
