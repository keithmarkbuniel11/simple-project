<template>
    <div>
        <Services />
        <Portfolio />
    </div>
</template>
<script>
import Services from './frontend/Services';
import Portfolio from './frontend/Portfolio';

export default {
  name: 'Home',
  components: {
    Services,
    Portfolio
  }
}
</script>