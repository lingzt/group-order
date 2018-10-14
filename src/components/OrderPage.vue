<template>
  <div class="OrderPage">
    <h1 v-text="pageTitle"></h1>

  <table>
    <thead>
      <tr>
        <th v-for="column in columns" :key="column">
          {{column}}
        </th>
      </tr>
    </thead>

    <tbody >
      <tr v-for="order in orders" :key="order.orderNumber">
        <td v-for="key in columns" :key="key" v-if="key == 'Price'" >
          {{order[camelCase(key)]}}
          <!-- <span :class='{dropdownBtn: index == 0}'  @click='dropdown'>{{tabItem}}</span>
          <ul v-if='index == 0' class="dropdownWrapper" v-show='dropdownActive'>
            <li v-for='(item, index) in paymentMethod' v-bind:key="index">{{item}}</li>
          </ul> -->
          <!-- <select>
            <option value="volvo">Volvo</option>
            <option value="saab">Saab</option>
            <option value="mercedes">Mercedes</option>
            <option value="audi">Audi</option>
          </select> -->
        </td>
      </tr>
    </tbody>

  </table>
  
    <ul>
      <li v-for="order in orders" :key="order.orderNumber">
        {{ order.orderNumber }} - {{ order.name}} {{ order.paidAmount}}
      </li>
    </ul>

  </div>

</template>

<script>
export default {
  name: 'OrderPage',
  data () {
    return {
      pageTitle: '22FL Biryani Group Order',
      columns: ['Order Number', 'type','Name','Plan B','Price','Paid via','Paid','Your Balance','change'],
      orders: [
        {
         orderNumber: '1',
         name: 'Mike G',
         type: 'type',
         planB:'',
         price:'12.8',
         paidVia:'',
         paid:'',
         yourBalance:'',
         change:''
        },
        {
         orderNumber: '2',
         name: 'TJ',
         type: 'type',
         planB:'',
         price:'12.8',
         paidVia:'',
         paid:'',
         yourBalance:'',
         change:''
        },
        {
         orderNumber: '3',
         name: 'Wendy Chen',
         type: 'type',
         planB:'',
         price:'12.8',
         paidVia:'',
         paid:'',
         yourBalance:'',
         change:''
        }
      ],
      paymentMethod: ['','Vemo', 'Chase Quick Pay', 'Apple Pay', 'Cash'],
      orderType:[
        {
          'Chicken R':'9',
          'Chicken L':'12.85',
          'Veggie R': '8',
          'Veggie L': '9.65',
          'Goat R': '10',
          'Goat L': '13.8',
          'Goat Tray':'90'
        }
      ]
    }
  },
  methods: {
    sortBy: function (key) {
      this.sortKey = key
      this.sortOrders[key] = this.sortOrders[key] * -1
    },
    camelCase: function (str) {
      return str.charAt(0).toLowerCase()+str.slice(1).replace(/\s+/g,"")
    }

  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
table {
  border: 2px solid #42b983;
  border-radius: 3px;
  background-color: #fff;
  margin: auto;
}

th {
  background-color: #42b983;
  color: rgba(255,255,255,0.66);
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  text-align: left;
}

td {
  background-color: #f9f9f9;
}

th, td {
  min-width: 120px;
  padding: 10px 20px;
}
a {
  color: #42b983;
}
</style>
