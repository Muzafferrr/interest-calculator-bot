<template>
  <div id="app">
    <div class="container">
      <div class="header">
        Future Interest Calculation
      </div>
      <div>
        <div class="content">
          <div class="leftText">You Will Calculate</div>
          <div class="rightField">Future value and interest amount</div>
        </div>
        <div class="content">
          <div class="leftText">Present Value(Capital)</div>
          <div class="rightField">
            <input type="text" v-model="capital" class="capitalInput">
          </div>
        </div>
        <div class="content">
          <span class="leftText">Interest Rate</span>
          <input type="text" v-model="rate" class="inputs">
          <select class="selectOption" v-model="rateType">
            <option value="Yearly" class="options">% Yearly</option>
            <option value="Monthly" class="options">% Monthly</option>
            <option value="Daily" class="options">% Daily</option>
          </select>
        </div>
        <div class="content">
          <span class="leftText">Term</span>
          <input type="text" v-model="termValue" class="inputs">
          <select v-model="term" class="selectOption">
            <option class="options" v-for="item in termArray" :value="item" :key="item">{{item}}</option>
          </select>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data(){
    return{
      capital: null,
      rate: 0,
      rateType: 'Yearly',
      termValue: 0,
      term: 'Year',
      termArray: ['Year','Month','Day']
    }
  },
  methods:{},
  computed:{},
  components: {}
}
</script>

<style>
.container{
  font-family: Arial, sans-serif;
  font-size: 15px;
  max-width: 600px;
  background-color: #f5f5f9;
  border-radius: 7px;
  box-shadow: 0 0 12px #888;
  margin-top: 20px;
  padding: 20px 10px 10px;
  margin-right: auto;
  margin-left: auto;
}

.header{
  font-weight: normal;
  padding-bottom: 5px;
  font-size: 17px;
  padding-top: 5px;
  width: 100%;
  text-shadow: 1px 1px 1px white;
  letter-spacing: 1px;
  text-align: center;
}

.content{
  margin-top: 20px;
  display: flex;
}

.leftText{
  width: 40%;
  align-items: center;
  justify-content: center;
  display: flex;
  font-size: 15px;
  color: #004372;
}

.rightField{
  font-size: 14px;
  width: 60%;
  display: flex;
  flex-direction: column;
}

.capitalInput{
  width: 95%;
  margin-top: 5px;
  margin-bottom: 5px;
  padding: 7px;
  border: solid 1px #e8e8e8;
  border-radius: 3px;
  box-shadow: 0 0 2px silver;
  font-size: 14px;
  resize: vertical;
}

.inputs{
  margin-top: 5px;
  margin-bottom: 5px;
  padding: 7px;
  border-radius: 3px;
  border: solid 1px #e8e8e8;
  box-shadow: 0 0 1px silver;
  font-size: 14px;
}

.selectOption{
  padding: 7px;
  border-radius: 3px;
  border: solid 1px #e8e8e8;
  box-shadow: 0 0 1px silver;
  font-size: 12px;
  margin: 5px 4px 5px 56px;
  width: 115px;
}

.options{
  display: block;
  white-space: pre;
  min-height: 1.2em;
  padding: 0 2px 1px;
}
</style>
