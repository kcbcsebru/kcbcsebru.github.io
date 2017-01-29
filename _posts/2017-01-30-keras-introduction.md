---
layout: post
title:  Keras  ডিপ লার্নিং লাইব্রেরি
subtitle:
published: true
---


Keras  পাইথনে লেখা একটি হাই লেভেল  নিউরাল নেটওয়ার্ক লাইব্রেরী , যা [TensorFlow](https://translate.googleusercontent.com/translate_c?depth=1&hl=en&ie=UTF8&prev=_t&rurl=translate.google.com&sl=auto&sp=nmt4&tl=bn&u=https://github.com/tensorflow/tensorflow&usg=ALkJrhjacqLUp1uimwz0Sng5XHIxHv7dcw) বা [Theano](https://translate.googleusercontent.com/translate_c?depth=1&hl=en&ie=UTF8&prev=_t&rurl=translate.google.com&sl=auto&sp=nmt4&tl=bn&u=https://github.com/Theano/Theano&usg=ALkJrhi8jp1slVZj-_Ui4rEA1D6MbC25VA) .এর উপর ভিত্তি করে রান করাইতে পারি  ।এটি দ্রুত পরীক্ষণশীল , এবং ইফিসিয়েন্ট গবেষণার অন্যতম  চাবিকাঠি ।*

### ডিপ লার্নিং এ  ` Keras `  কেন ব্যবহার করবো   ?

-   **Modularity, minimalism, এবং extensibility**  এর মাধ্যমে  সহজ এবং দ্রুত প্রোটোটাইপিং জন্য অনুমতি দেয়.
-    convolutional networks এবং  recurrent networks  অথবা এরদের দুইটিরই সমন্বয় সমর্থন করে.
-   মাল্টি ইনপুট এবং মাল্টি আউটপুট ট্রেইনিং সমর্থন করে.
-   CPU ও GPU উভয় প্লার্টফর্মেই সমানভাবে কাজ করে.

**পাইথন 2.7-3.5:** Keras এর সঙ্গে সামঞ্জস্যপূর্ণ  । 

------

## মূলনীতি আলোচনা

-   **Modularity.** একটি মডেল হল  একটি  sequence অথবা  একটি সতন্ত্র graph কিংবা সম্পূর্ণরূপে কনফিগার করা মডিউল যা , সামান্য রেস্ট্রিক্সনের মাধ্যমে  কনফিগার করা যেতে পারে .। বিশেষ করে, , neural layers, cost functions, optimizers, initialization schemes, activation functions, regularization schemes  সব স্বতন্ত্র মডিউল আপনাকে নতুন একটি  মডেল তৈরি করতে সাহায্য করে ।
-   **Minimalism.** প্রতিটি মডিউল ছোট এবং সহজ রাখা উচিত যাতে কোডের প্রতিটি স্থান  স্বচ্ছভাবে সহজেই পড়া যেতে পারে ।
-   **Easy Extensibility**. নতুন মডিউল  (নতুন ক্লাস এবং ফাংশন হিসাবে) যোগ করা জন্য সহজ হয়, এবং বর্তমানে  বিদ্যমান মডিউল সমুহের অনেক উদাহরন দেয়া আছে সহজে নতুন মডিউল তৈরি করা যায় যা দ্রুত পরীক্ষণশীল , এবং ইফিসিয়েন্ট গবেষণার অন্যতম  চাবিকাঠি ।
-   **পাইথন সাথে কাজ করুন.** মডেল বর্ননা করার জন্য  কোন পৃথক মডেল কনফিগারেশন ফাইলের দরকার হয়না  । মডেলগুলো  পাইথন কোড দিয়ে বর্নিত থাকে যা কম্প্যাক্ট এবং  ডিবাগ করা খুব সহজ, এবং যা সহজেই বর্ধিত করা সম্ভব । 

------

## শুরুর দিকের কথা :  30 সেকেন্ডে Keras

 লেয়ার গুলোকে  সংগঠিত করার জন্য  মডেল হচ্ছে Keras এর  কোর ডাটা স্ট্রাকচার । মডেলের  প্রধান টাইপ হচ্ছে  [`Sequential`](https://translate.googleusercontent.com/translate_c?depth=1&hl=en&ie=UTF8&prev=_t&rurl=translate.google.com&sl=auto&sp=nmt4&tl=bn&u=http://keras.io/getting-started/sequential-model-guide&usg=ALkJrhjL9Po8_yRhTDoX83-EnFbOX-SYuA) মডেল, লেয়ার গুলোর  একটি লিনিয়ার স্ট্যাক। আরো জটিল আর্কিটেকচারের জন্য, আপনি  [Keras এর ফাংশনাল এপিআই](https://translate.googleusercontent.com/translate_c?depth=1&hl=en&ie=UTF8&prev=_t&rurl=translate.google.com&sl=auto&sp=nmt4&tl=bn&u=http://keras.io/getting-started/functional-api-guide&usg=ALkJrhhlVaE0sqB-H1A7sZCFhwSmwV7XYA)   ব্যবহার করতে পারেন । 

এখানে `Sequentia `  `Model`  টি ঠিক এরকম হতে পারে   :

```python
from keras.models import Sequential
model = Sequential() 
```

লেয়ার গুলোকে সহজেই   stacking করা যায়   `model.add() ` ফাংশন দিয়ে   :

```python
from keras.layers import Dense, Activation 
model.add(Dense(output_dim=64, input_dim=100)) 
model.add(Activation("relu")) 
model.add(Dense(output_dim=10)) 
model.add(Activation("softmax")) 
```

এখন আপনার মডেল তৈরি  । তাই এর সাথে  লার্নিং প্রসেস কনফিগার `model.compile()` করতে পারি ঠিক এইভাবে  :

```python
model.compile(loss='categorical_crossentropy', optimizer='sgd', metrics=['accuracy']) 
```

এখন যদি আপনি প্রয়োজন বোধ করেন, তাহলে আপনি আরও অপ্টিমাইজার কনফিগার করতে পারেন. 

```python
from keras.optimizers import SGD 
model.compile(loss='categorical_crossentropy', optimizer=SGD(lr=0.01, momentum=0.9, nesterov=True)) 
```

এখন আপনি ব্যাচে আপনার প্রশিক্ষণ ডাটা উপর ইটারেশন চালাতে পারেন:

```python
 model.fit(X_train, Y_train, nb_epoch=5, batch_size=32) 
```

অন্যথা, আপনি নিজে আপনার মডেল ব্যাচে ডাটা ফিড করাতে  পারেন:

```python
 model.train_on_batch(X_batch, Y_batch) 
```

তারপর আপনার মডেলের কর্মক্ষমতা মূল্যায়ন:

```python
 loss_and_metrics = model.evaluate(X_test, Y_test, batch_size=32) 
```

অথবা নতুন ডাটার উপর ভবিষ্যৎবাণী করতে পারেন :

```python
classes = model.predict_classes(X_test, batch_size=32) proba = model.predict_proba(X_test, batch_size=32) 
```

একটি আটোমেটিক প্রশ্নের উত্তর সিস্টেম নির্মাণের প্রণালী, একটি ছবি সংগ্রহ মডেল, একটি নিউরাল টুরিং মেশিন, একটি word2vec embedder বা অন্য কোন মডেল যেহেতু দ্রুত চিন্তা করা যায়  তাই  তাদের বাস্তবায়ন  কেন বেদনাদায়ক হওয়া উচিত  ? এই জন্যই আমরা কেরাস লাইব্রেরী ব্যাবহার করবো । 



