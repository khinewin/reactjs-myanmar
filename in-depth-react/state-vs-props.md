# State vs Props

## React State System

State ဆိုတာ JavaScript Object တစ်ခုဖြစ်ပြီးတော့ Component တစ်ခုရဲ့ data အပြောင်းအလဲကို ယာယီသိမ်းတဲ့အခါ သုံးတယ်။ နောက် ကျွန်တော်တို့ Component တွေ ဖန်တီးတဲ့အခါ Class-based component နဲ့ functional component ဆိုပြီး ၂ မျိုးရှိတယ်။ Component တစ်ခုက state နဲ့ အလုပ်လုပ်တော့မယ်ဆိုရင် ကျွန်တော်တို့က ဒီ Component ကို Stateful Component လို့ခေါ်တယ်။

> State ပါတဲ့ component တစ်ခုကို Stateful Component လို့ခေါ်ပြီး state မပါတဲ့ component ကို Stateless Component လို့ခေါ်တယ်။

```javascript
class App extends Component {
  constructor(props) {
    super(props);
      this.state = { title: 'ReactJS State System' }
  }
  render() {
    return(
     <div>I'm learning { this.state.title }</div>
    )
   }
}
```

`this.state` နဲ့ component တစ်ခုရဲ့ state ကို သတ်မှတ်လို့ရသလို state data ကိုလည်းပြန် ပြောင်းလို့ရပါတယ်။ နောက်တစ်ခုက state ပြောင်းလဲမှုတွေက asynchronous အနေနဲ့ပြောင်းလဲသွားနိုင်တယ်။ အောက်က နမူနာမှာ component ရဲ့ state data ကို ဘယ်လို ပြောင်းလဲရမလဲဆိုတော့

```javascript
class App extends Component {
  constructor(props) {
  super(props);
    this.state = { data: 'click the button to see what happen' }
  } 
  
  onDataChange = () => {
   this.setState({ data: 'Data changed from State' })
  }
  
  render() {
    return(
      <div>
        <div>{ this.state.data }</div>
        <button onClick={this.onDataChange}>change text</button>
       </div>
    )
  }
}
```

`this.setState` ကိုသုံးပြီး Component တစ်ခုရဲ့ state data ကိုပြောင်းလဲပြီးပြီ…ဒါက ကျွန်တော်တို့ Component တစ်ခုအတွင်းမှာပါ။ ဒါဆို Component တစ်ခုနဲ့တစ်ခု ဘယ်လို Data ဘယ်လိုပို့ကြမလဲ။အိုကေ…စိတ်ဝင်စားစရာပဲ..ဆက်ကြည့်ရအောင်။

## ReactJS Props \(Properties\) System

`Props` ဆိုတာ ဘယ်ချိန်မှာ ဖြစ်ပေါ်လာတာလည်းဆိုတော့ Parent Component ကနေ Child Component ဆီ data ပို့တဲ့အခါ ဖြစ်ပေါ်လာတာပါ။ `Props` ရဲ့ data ကို ပြောင်းလို့မရပါဘူး…ဘာလို့လဲဆိုတော့ Child Component မှာ `state` သုံးပြီး ပို့လာတဲ့ data ကို `props` အနေနဲ့လက်ခံတယ်။ ခုနက `state` ကို Parent Component အတွင်းမှာ define လုပ်ပြီးပို့တယ်…ဆိုတော့ State နဲ့ Props ရဲ့ ကွာခြားချက်က `State` က changes ဖြစ်တယ်။ `Props` က immutable ဖြစ်တယ်။ Let’s take a look at an example

```javascript
// App is parent component
class App extends React.Component {
  state = {
    text: 'Date comes from header';
  }
  render() {
    return (
      <div>
        <Header headerText={this.state.text} />
        // headerText is props to pass down child component
      </div>
    )
  }
}

// Header is child component
class Header extends React.Component {
  render() {
    // Here received parent state data as props
    return <div>{this.props.headerText}</div>
  }
}
```

