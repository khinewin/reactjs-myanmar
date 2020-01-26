# Template literals

**Template literals** ကတော့ strings တွေကို နည်းလမ်အသစ်နဲ့အလုပ်လုပ်လို့ရအောင် မိတ်ဆက်ပေးလိုက်တဲ့ feature တစ်ခုပါ။ ES5 မှာတုန်းက string ကို `double quotes`, `single quote` တွေနဲ့ရေးပါတယ်။ ဒီ template literals မှာတော့ `backtick` ကိုပဲသုံးပါတယ်။

```javascript
const name = `Nay Yaung Lin Lakk`;
const age = 17;
```

ရိုးရှင်းတယ် လွယ်ကူတယ် ဒါ့အပြင် normal string တွေမလုပ်နိုင်တဲ့ အရာကို ဒီမှာ လုပ်လို့ရပါတယ်။ ဥပမာ

1. multiline string တွေရေးတဲ့အခါ အဆင်ပြေတယ် 
2. variable တွေ expression တွေကို string နဲ့တွဲရေးရတာအခါလည်းအဆင်နဲ့တွဲရေးရတာအခါလည်းအဆင်ပြေတယ်

### Multiline string

multiple line တွေရေးဖို့အတွက် ကျွန်တော်တို့ `\n` ကိုအသုံးပြုရပါတယ်။

```javascript
const text = 
    `Hello \
I am Raymond`; 

// Hello I am Raymond
```

```javascript
const text = 
    `Hello \n \
I am Raymond`; 

//Hello 
// I am Raymond
```

backtick ထဲမှာကိုယ်ရေးရင် ရေးတဲ့အတိုင်း render ပြန်ပါလိမ့်မယ်။ HTML ရဲ့  `<pre>`t ag လိုပေါ့

```javascript
const string = `First
                Second`
```

```javascript
First
                Second
```

backtick ရဲ့ အဆုံးမှာ trim ဆိုတဲ့ built-in function ထည့်သုံးလိုက်ရင် character တွေရဲ့အရှေ့မှာပိုနေတဲ့ space တွေကိုဖယ်ပေးပါလိမ့်မယ်။

```javascript
const string = `
First
Second`.trim()
```

### **Interpolation**

Template literals က ကျွန်တော်တို့ကို string တွေထဲမှာ variables တွေ expression တွေ တိုက်ရိုက်ခေါ်ယူသုံးနိုင်အောင် လုပ်ပေးထားပါတယ်။ syntax တည်ဆောက်ပုံက ```${...}```

```javascript
const name = "Raymond";
const sayName = `Hello, I am ${name}`; //Hello, I am Raymond
```

```javascript
const status = true;
const renderElement = `${status ? 'Rendered' : 'Something went wrong'}`;
```





