<template>
  <div class="alert alert-success alert-dismissable">
	<button type="button" class="close" data-dismiss="alert"
			aria-hidden="true">
		&times;
	</button>
	{{message}}
</div>
</template>

<script>
export default {
  name: 'alert',
  props: ["message"],
}
</script>

<style scoped>

</style>
