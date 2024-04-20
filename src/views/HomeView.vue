<script>
/* Example in Node.js */

const axios = require('axios'); // hier krijg ik dus een error code
// import axios from 'axios'; Hier krijg ik geen error code maar allerlei andere errors

let response = null;
new Promise(async (resolve, reject) => {
  try {
    response = await axios.get('https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest', {
      headers: {
        'X-CMC_PRO_API_KEY': '16749118-b7c5-420c-9fb8-15ed1253abe0',
        // api key hierboven is dus mijn eigen API key
      },
    });
  } catch(ex) {
    response = null;
    // error
    console.log(ex);
    reject(ex);
  }
  if (response) {
    // success
    const json = response.data;
    console.log(json);
    resolve(json);
  }
});

</script>

<template>

</template>
