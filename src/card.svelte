<script>
  import 'wired-elements';
</script>

<style>
  wired-card {
  }
  h3 {
    color: var(--highlight);
  }
</style>

<wired-card elevation='2'>
  <h3><slot name="title"></slot></h3><br />
  <p><slot name="body"></slot></p>
</wired-card>
