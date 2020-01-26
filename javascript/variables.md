---
description: JavaScript မှာ data တန်ဖိုးတွေသိမ်းတဲ့အခါ အသုံးပြုပါတယ်
---

# Variables

JavaScript မှာ variables တွေကို `var` , `let`, `const` ဆိုပြီး ၃မျိုး ကြော်ငြာ \(declare\) လို့ရပါတယ်။ JavaScript variables တွေကြော်ငြာတဲ့အခါ type ထည့်ပေးစရာမလိုပါဘူး။

variable ကို declare လုပ်တယ်ဆိုတာက identifier လေးသတ်မှတ်ပေးတာပါ။ 

```javascript
var x; //typeof x === 'undefined'
```

x ဆိုတာက identifier ပါ။ ဒီလို ‌အခြေအနေမျိုးမှာ x ရဲ့တန်ဖိုးက undefined ပါ။

variable assign လုပ်တယ်ဆိုတာက တန်ဖိုးတစ်ခုသွားထည့်လိုက်တာပါ။

## Using var

ES2015 မတိုင်ခင်အထိ var ဆိုတာကို variables တွေကြော်ငြာဖို့အတွက်သာ သုံးခဲ့တယ်။ var ကိုအသုံးပြုပြီးတော့ variable တစ်ခုရဲ့တန်ဖိုးကို ထပ်ခါထပ်ခါ ကြော်ငြာနိုင်ပါတယ်။

```javascript
var a = 1;
var a = 2;
```

variables တွေအများကြီးကိုတစ်ကြောင်းတည်းနဲ့လည်းကြော်ငြာနိုင်ပါတယ်

```javascript
var a = 1, b = 2;
```

## Scope

function ရဲ့အပြင်ဘက်မှာ var သုံးပြီး ကြော်ငြာထားတဲ့ variable တစ်ခုကို global object အနေနဲ့ သတ်မှတ်ပါတယ်။ သူ့မှာ global scope ရှိပြီး program ရဲ့ကြိုက်တဲ့နေရာကနေ access လုပ်ယူနိုင်ပါတယ်။ function တစ်ခု ထဲမှာ var သုံးပြီးကြော်ငြာထားတဲ့ variable ကို local scope လို့ခေါ်ပါတယ်။ သူ့ကိုကြော်ငြာထားတဲ့ function အထဲမှာသာလျှင် အသုံးပြုနိုင်ပါတယ်။ES2015 မတိုင်ခင် JavaScript မှာ Global scope နဲ့ Function scope ပဲရှိခဲ့ပါတယ်။

```javascript
// code here can NOT use name

function myFunction() {
  var name = "JavaScript";

  // code here CAN use name

}
```

> Local variables တွေက function တစ်ခုစအလုပ်လုပ်ရင် သူတို့ပါအလုပ်လုပ်ပြီး function တစ်ခု အလုပ်ပြီးသွားရင် သူတို့ပါ လိုက်ပြီးမြောက်တယ်

## Using Let

`let` နဲ့ `const` ဆိုတာကတော့ ES2015 မှာ စတင်မိတ်ဆက်ခဲ့တဲ့ features နှစ်ခုပါ။ ၂ခုစလုံးမှာ Block scope တွေရှိပါတယ်။

> Block Scope ဆိုတာက if, switch, while, for စတဲ့ control statement တွေအတွင်းမှာရှိတာကိုပြောတာပါ။

```javascript
{
  var x = 2;
}
// x CAN be used here
```

```javascript
function foo(){
    if(true){
        var fruit1 = 'apple';        //exist in function scope
        const fruit2 = 'banana';     //exist in block scope
        let fruit3 = 'strawberry';   //exist in block scope

    }
    console.log(fruit1);
    console.log(fruit2);
    console.log(fruit3);
}

foo();
//result:
//apple
//error: fruit2 is not defined
//error: fruit3 is not defined
```

`var` မှာ block scope မရှိတဲ့အတွက် if block အပြင်ကနေ ခေါ်ယူသုံးပြီး console ထဲမှာ ပြန်ထုတ်ထားပါတယ် ကျန်တဲ့ `const`တို့ `let` တို့က not defined ဆိုတဲ့ error တွေ့ရပါတယ်။

## Using const

`var` တို့ `let` တို့နဲ့ ကြော်ငြာထားတဲ့ variable တွေကို program ရဲ့ နောက်ဆုံးဖြစ်ဖြစ် လိုအပ်ချက်အရ တန်ဖိုးကို ပြန်သတ်မှတ်ရတာမျိုးတွေရှိပါတယ်။ const ကိုသုံးပြီး ကြော်ငြာထားတဲ့ variable ရဲ့တန်ဖိုးကို ဘယ်တော့မှ ပြန်ပြောင်းလို့မရတော့ပါဘူး။

```javascript
const a = 'test';
```

`const` လည်းပဲ `let` လို `Block Scope` ရှိပါတယ်။

JavaScript developers တွေအနေနဲ့ variable ကြော်ငြာတဲ့အခါ နောက်ထပ် တန်ဖိုးပြန်မပြောင်းနိုင်တဲ့ ကောင်တွေကို `const` သုံးပြီးကြော်ငြာပေးသင့်ပါတယ်။ variable တစ်ခုကို တန်ဖိုးပြန်သတ်မှတ်ချင် \( reassign \) ရင် `let` ကိုသုံးပါ







