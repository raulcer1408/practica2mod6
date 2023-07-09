<template>
    <div>
        <footer :style="'background-color:'+footerColor">    
        </footer>
    </div>
  </template>
  
  <script>
  export default {
    name: 'FootN',
    props: {
        
    },
    data(){
       return {
        footerColor: "slategrey",
       }
    },
    created() {
        
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
 footer {
                
                text-align: center;
                padding: 30px 10px;
                margin-top: 50px;
                min-height: 100px;
            }
  </style>