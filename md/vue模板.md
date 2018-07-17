<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <link rel="stylesheet" href="https://cdn.bootcss.com/animate.css/3.5.2/animate.min.css">
  <script src="https://cdn.jsdelivr.net/npm/vue"></script>
</head>
<body>
  <div id="app">
    <my-component></my-component>
  </div>
  <template id="component">
    <div>
      <h1 id="title">
        this is a {{ message }}
      </h1>
    </div>
  </template>  
 <script>
    Vue.component("my-component", {
      template: "#component",     
      data () {
        return {
          message: 'component'
        }
      }
    })
    new Vue({
      el: '#app'
    })
    
  </script>
</body>
</html>