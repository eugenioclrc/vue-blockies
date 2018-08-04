<template>
  <img :src="dataurl" />
</template>

<script>
import blockies from 'ethereum-blockies';
// import hqx from 'js-hqx';

// if i dont do this the first random is black :S
blockies.create({});

/**
OPTS
{ // All options are optional
    seed: 'randstring', // seed used to generate icon data, default: random
    color: '#dfe', // to manually specify the icon color, default: random
    bgcolor: '#aaa', // choose a different background color, default: random
    size: 15, // width/height of the icon in blocks, default: 8
    scale: 3, // width/height of each block in pixels, default: 4
    spotcolor: '#000' // each pixel has a 13% chance of being of a third color,
    // default: random. Set to -1 to disable it. These "spots" create structures
    // that look like eyes, mouths and noses.
}
*/


export default {
  name: 'blockies',
  props: {
    opts: Object,
  },
  computed: {
    dataurl() {
      const icon = blockies.create(this.opts);
      /*
      TBD ?
      const img = document.createElement('img');
      img.onload = () => {
        hqx(img, 2)
      };
      img.src = icon.toDataURL();
      */

      return icon.toDataURL();
    }
  },
}
</script>
