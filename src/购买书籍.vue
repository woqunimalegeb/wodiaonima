template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
      <li v-for="(obj,index) in arr" :key="index">{{obj.name}} <button @click="btn(index)">买书</button></li>
    </ul>
    <table border="1" width="500" cellspacing="0">
      <tr>
        <th>序号</th>
        <th>书名</th>
        <th>单价</th>
        <th>数量</th>
        <th>合计</th>
      </tr>
      <tbody>
        <tr v-for="(obj,index) in arr" :key="index">
          <td>{{index+1}}</td>
          <td>{{obj.name}}</td>
          <td>{{obj.price}}</td>
          <td>{{obj.count}}</td>
          <td>{{obj.count*obj.price}}</td>
        </tr>
      </tbody>
    </table>
    <p>总价格为:{{sum}} </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          name: "水浒传",
          price: 107,
          count: 0,
        },
        {
          name: "西游记",
          price: 192,
          count: 0,
        },
        {
          name: "三国演义",
          price: 219,
          count: 0,
        },
        {
          name: "红楼梦",
          price: 178,
          count: 0,
        },
      ],
    };
  },
  methods:{
    btn(index){
this.arr[index].count++
    }
  },
  computed:{
    sum(){
     
return this.arr.reduce((num,obj)=>{
  console.log(num,obj);
 return (num+=obj.count*obj.price)
},0)
    }
  }
};
</script>

<style scoped>
td{
  text-align: center;
}
li{
  list-style: none;
  margin-bottom: 10px;
}
</style>
