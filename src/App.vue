<template>
  <div id="app">

    <div class="container">
      <h2 align="center">Work Shop #3 คำนวณราคาสินค้า</h2>
      <hr>
      <div class="row">
        <div class="col-md-2" v-for="item in products">
          <div class="card h-100">
            <img :src="item.image" class="card-img-top" alt="...">
            
            <div class="card-body">
              <h4 class="card-title">{{item.name}}</h4>
              <p class="card-text"> ราคา {{item.price}} บาท</p>
            </div>

            <div class="card-footer">
              <input type="checkbox" @change="selected(item)">
            </div>
          </div>
        </div>

        <div class="total-price">
          <h4>ยอดชำระเงิน {{total()}} บาท</h4>
        </div>
      </div>
      
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      products:[
        {
          id:1,
          name:'กาแฟเย็น',
          price: 50,
          image: 'https://media.istockphoto.com/photos/black-russian-cocktail-picture-id927104472?b=1&k=20&m=927104472&s=170667a&w=0&h=aYIBp0LJv1P4b_9Qkf-xEesCMWvCB1bf1LRifA4Q8qw=',
          active: false
        },
        {
          id:2,
          name:'โกโก้เย็น',
          price: 55,
          image: 'https://media.istockphoto.com/photos/iced-chocolate-drink-picture-id691613358?b=1&k=20&m=691613358&s=170667a&w=0&h=y7ShRs-8V9C9waJfQhppNugt9hlQ6n0or1iTNsOOKYI=',
          active: false
        },
        {
          id:3,
          name:'ชาเขียวเย็น',
          price: 55,
          image: 'https://media.istockphoto.com/photos/two-glasses-with-iced-green-matcha-tea-with-lime-ice-fresh-mint-and-picture-id1250502618?b=1&k=20&m=1250502618&s=170667a&w=0&h=i1249_-FMD9NBu0qiDbbUZEliGjAq5z86KcM-ffRj0o=',
          active: false
        },
        {
          id:4,
          name:'ช็อกโกแลตปั่น',
          price: 60,
          image:'https://images.unsplash.com/photo-1528740096961-3798add19cb7?ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8Y2hvY28lMjBpY2V8ZW58MHx8MHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60',
          active: false
        },
        {
          id:5,
          name:'น้ำส้มปั่น',
          price: 60,
          image:'https://media.istockphoto.com/photos/shot-of-fresh-orange-juice-in-a-glass-picture-id1225546255?b=1&k=20&m=1225546255&s=170667a&w=0&h=BzHMJEjZmMg3riWXAY65k1jQv9cIOzOlzD9kqkkRcB0=',
          active: false
        },
        {
          id:6,
          name:'น้ำสรอเบอร์รี่ปั่น',
          price: 60,
          image:'https://media.istockphoto.com/photos/some-glasses-with-strawberry-liqueur-picture-id178416773?b=1&k=20&m=178416773&s=170667a&w=0&h=mpXzzrktd8siVE3diq07wAMU1o4oiRzLO9DeT1lWyVg=',
          active: false
        }
      ]
    }
  },
  methods: {
    selected:function(item){
      item.active = !item.active
    },
    total:function(){
      var sum = 0;
      this.products.forEach(function(item){
        if(item.active){
          sum += item.price;
        }
      });
      return sum;
    }

  }
}

</script>

<style>

  *{
    margin:0;
    padding:0;
    box-sizing: border-box;
  }

  .container{
    max-width:1280px;
    margin-top:15px;
    widht:100%;
  }

</style>
