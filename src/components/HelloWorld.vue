<script>
// import ChartView from '@/components/ChartView';
import {  ref} from 'vue'

export default {
  name: 'HelloWorld',
  components: {
    Clock: {
      props: {
        counter1: Number
      },
      setup(props) {
        const r = () => {
          return <div id="clock"> {props.counter1}</div>
        }
        return r
      }
    }
  },
  setup() {

    // const count = ref(0)
    // setInterval(() => {
    //   count.value = count.value + 1
    // }, 1000)
    // const r = () => {
    //   return <div id="clock"> {count.value}</div>
    // }

    const count = ref(0)
    setInterval(() => {
      count.value = count.value + 1
      console.clear()
    }, 1000)
    const renderParent = () => {
      return <div id="parent">
        <div id="child-1">
          <p id= "p1">  hello world </p>
          <p id= "p2">  hello world </p>
        </div>
        <p id="p3"> hello world </p>
        <clock counter1={count.value}/>
      </div>
    }
    return () => renderParent()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
