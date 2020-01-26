# How does React work?

အောက်က code က React example Hello World ဆိုပါစို. 

```javascript
class Hello extends React.Component { 
    render() { 
        return <h1>Hello, {this.props.name}!</h1>
    }
}
```

အပေါ်က code example လေးကိုသုံးပြီး React က internally ဘယ်လိုအလုပ်လုပ်သွားလဲဆိုတာ ကြည့်ရအောင်ပါ။ ပထမဆုံး React က ES6 class တွေကိုသုံးလို.ရတယ်။ ES6 မှာ JS မှာ class တွေသုံးလို.ရပြီ။ တကယ်က Browser မှာ run နေတဲ့ JS အများစုက အဲ့လို feature တွေသုံးလို.မရဘူး။ အဲ့တော့ဘယ်လိုလုပ်ရလဲဆိုရင် ES6 ကနေ ES5 ကိုပြောင်းပစ်ရတယ် ဆိုချင်တာက ခုနက class Hello အစရှိတာတွေကို browser က နားလည်တဲ့ သာမာန် JS အနေနဲ. transpile လုပ်တယ်။ အဲ့အလုပ်ကို Babel transpiler ကလုပ်ပေးတယ်။

React component တွေမှာ မပါမဖြစ်က render method, အဲ့ထဲမှာ component ရဲ. UI element တွေကိုထဲ့ရေးတယ်။ အဲ့နေရာမှာ JSX ကိုသုံးလို.ရတယ်။ အောက်က ကောင်သည် JSX statement ပဲ

```javascript
Hello, {this.props.name}!
```

JavaScript and XML ပေါ့။ JSX ကို browser က နားလည်လားဆိုတော့ နားမလည်ဘူး အဓိက UI markup ရေးရတာ အဆင်ပြေလို.သူ.ကိုထဲ့ထားတာ။ အဲ့တော့ ခုနက JSX ကို browser နားလည်တဲ့ JS statement တွေဖြစ်အောင်ပြောင်းတယ် အဲ့တာကို JSX compiler က လုပ်တယ်။ JSX compiler က ဘယ်လိုအလုပ်လုပ်သလဲဆိုရင် ရှင်းပါတယ် JSX expression တွေ ကိုယူပြီးတော့ Regular expression သုံးပြီး တော့ JS statement တွေထုတ်တာ။ဒါဆိုခုနက JSX အတွက်ဆို ဒါမျိုးရမယ်။

```javascript
React.createElement("h1", null, "Hello, ", (void 0).props.name, "!");
```

React.createElement သည် ဘာလဲဆိုတော့ React ကသုံးတဲ့ virtual dom representation ပဲ။ React က ဘာလို. Virtual DOM ကိုသုံးလဲဆိုရင် real DOM သည် နှေးလို. ဘာလို.နှေးတာလဲဆိုရင် ဥပမာ UI မှာ style တခုခုကိုပြင်လိုက်မယ်စိုပါစို. ဒါဆိုရင် JS engine ကနေ rendering engine WebKit လိုကောင်ကိုသွားရတယ်။ နောက်ပြီး the whole page အတွက် UI layout တွေပြန်တွက်တာလုပ်ရတယ်။ နောက် paint လုပ်ရတယ် အဲ့တော့ ခုနက လို UI changes ခနခန လုပ်လေ အဲ့တာတွေ တွက်ရလေ နောက် JS engine နဲ. DOM rendering engine ကြား context switch လုပ်ရသေးတယ်။ အဲ့တော့ အဲ့လို style တခု တခါ page reflow လုပ်မဲ့အစား UI changes အားလုံးကို တခါတည်းစုပြင်မယ် ဒါဆိုရင် ပိုမြန်မယ်။ နောက်ပြီးတော့ ဥပမာ list 10 ခုရှိတယ် အဲ့ထဲက ၂ ခုလောက်ပဲပြင်မယ်ဆိုရင် အားလုံးကို အစကနေ မလုပ်ပဲ လိုတဲ့ ၂ ခုကိုပဲ ကွက်ပြင်မယ်။ ဒီလိုဆိုရင်ပိုမြန်မယ်ပေါ့။

Graphic programing မှာသုံးတဲ့ double buffering နဲ.သဘောတူတယ်။ ဆိုချင်တာက in memory representation မှာစိတ်ကြိုက်ပြင်ပြီး လိုတဲ့ကောင်ကို changes ကို DOM မှာ တခါတည်း batch အလိုက်ပြင်လိုက်တာ အဲ့တော့ပိုမြန်မယ်။ ခုနက React.createElement ကရလာတွေသည် virtual dom node လေးတွေ။

Virtual DOM node ဆိုတော့ သူ.က real dom မဟုတ်ဘူး။ အဲ့တော့ ခုနက virtual DOM ကို real dom ဖြစ်အောင်ပြောင်းရမယ်။ အဲ့တာကို ဒီလိုလုပ်တယ်။

```javascript
ReactDOM.render(, document.getElementById('main'))
```

ခုနက React createElement က ရလာတဲ့ virtual DOM ကို ReactDOM renderer က Real DOM ဖြစ်အောင်ပြောင်းပစ်တယ် ဘယ်လိုပြောင်းလဲဆိုတော့ virtual dom ရဲ. node type တွေပေါ်မူတည်ပြီး document.createElement လို DOM API တွေသုံးပြီး create လုပ်တယ်။ ပြီးတော့အဲ့တာကို တကယ့် real dom node မှာထဲ့လိုက်တယ်။ Event တွေကိုကျတော့ element တခုချင်းဆီဖို. event တခုမဆောက်ပဲ အားလုံးအတွက် caputure လုပ်တယ် ပိုမြန်အောင်။

React က component ရဲ. UI ကိုပြောင်းစေချင်ရင် \(render လုပ်စေချင်ရင\)setState ကိုခေါ်ရတယ်။ setState ကထွက်လာတဲ့ virtual DOm အသစ်နဲ. နဂိုအဟောင်းကို တိုက်စစ်တယ်။ DOM tree difference ကိုရှာတယ် လိုတဲ့အပိုင်းကိုပဲပြင်တယ်။ ဒါကို reconciliation algorithm ကလုပ်တယ်။

Reconciliation algorithm ဆိုတာ virtual dom tree အဟောင်းနဲ.အသစ်ကြား ဘာတွေပြောင်းသွားလဲဆိုတာကို heuristic တွေသုံးပြီး ဥပမာ id က အဟောင်းဆိုရင် node ကမပြောင်းဘူး။ content ပြောင်းသလား root node ချင်း type ပြောင်းသွားရင် အသစ်ပြန်ဆောက်ရမယ်။ ဒါမျိုးတွက်ယူတယ်။

Life Cycle method တွေကတော့ framework က သူ. step တွေအတိုင်းအလုပ်လုပ်သွားတာ။နောက်ဆုံး Fiber implementation မှာတော့ tree ကို asynchronously render လုပ်လို.ရအောင်လုပ်ပေးထားတယ်။

