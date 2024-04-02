<template>
  <div>
    <input type="file" @change="uploadFile" />
  </div>
</template>

<script setup>
import OSS from 'ali-oss';

const uploadFile = async function(event) {
  const client = new OSS({
    region: '<Your OSS region>',
    accessKeyId: '<Your AccessKey ID>',
    accessKeySecret: '<Your AccessKey Secret>',
    bucket: '<Your Bucket name>',
  });

  try {
    const file = event.target.files[0];
    const result = await client.put('<Your file path in OSS>', file);
    console.log('File uploaded successfully:', result);
  } catch (error) {
    console.error('Error uploading file:', error);
  }
}

</script>