<template>
  <li>
      <span class="author">{{ author }} : </span>
      <span class="text">{{ text }}</span>
      <span class="time-stamp">{{ timestamp }}</span>
  </li>
</template>

<script>
    export default {
        props: ["author", "text", "timestamp"]
    };
</script>

 <style>

    body{
     padding:10px;
    }

    .author{
     font-weight:bold;
     font-size:16px;
    }

    .time-stamp{
     position: absolute;
     font-size: 10px;
     right: 6px;
     bottom: 5px;
     padding: 2px 5px;
    }

 </style>
