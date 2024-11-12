<template>
  <div>
  <Navbar/>
  
    <NuxtPage/>
  </div>
</template>
<script>
import 'uikit/dist/css/uikit.min.css';
import UIkit from 'uikit';
import Icons from 'uikit/dist/js/uikit-icons';
UIkit.use(Icons);

</script>

<style>
/* Global button style for consistency */
.uk-button-primary, .uk-button-secondary {
  background-color: #B76E3B; /* Copper */
  color: #FFFFF0; /* Ivory */
  border-radius: 4px;
  transition: background-color 0.3s ease;
}

.uk-button-primary:hover, .uk-button-secondary:hover {
  background-color: #A95D30; /* Darker Copper shade */
}
</style>