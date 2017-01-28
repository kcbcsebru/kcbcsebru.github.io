---
layout: post
title: Introduction to Deep Learning in Python.
subtitle: Deep Learning in Python .
published: true
---

## পাইথন , কেরাস এবং  ডিপ লার্নিংঃ

**ডিপ লার্নিংঃ**

সায়েন্স ফিকশন বয়সের দিক থেকে শতবর্ষ পেরিয়ে গেছে। সায়েন্স ফিকশনগুলোর শুরুর দিক থেকেই আমরা কৃত্রিম বুদ্ধিমত্তাসম্পন্ন যন্ত্রের দেখা পেয়ে আসছি। বাস্তবে এখনও বুদ্ধিমত্তার সেই স্তরে পৌঁছানো সম্ভব হয়নি মানুষের পক্ষে। তবে সেই পথে অনেকটাই এগিয়ে গেছে মানুষ। কম্পিউটিংয়ের গতিশীল ধারায় এমন প্রযুক্তি মানুষ উদ্ভাবন করতে সমর্থ হয়েছে, যাতে করে এখন যন্ত্রমানবেরা সনাক্ত করতে সক্ষম হচ্ছে বস্তুকে। এখন যন্ত্রের মাধ্যমে রিয়েল-টাইমে এক ভাষা থেকে অন্য ভাষায় অনুবাদ পাওয়া যাচ্ছে। যন্ত্রের এই শিক্ষণ-পদ্ধতিকেই বলা হচ্ছে 'ডিপ লার্নিং'।  "ডিপ লার্নিং" , ডিপ স্ট্রাকচারড লার্নিং, হায়ারারকিকাল লার্নিং বা ডিপ মেশিন লার্নিং নামেও পরিচিত ।

 ডিপ-লার্নিং সিস্টেম প্রযুক্তি  নিয়ে কাজ করছে , তাদের মধ্যে  ইউটিউব থেকে প্রায় ১০ মিলিয়ন ছবি বাছাই করে প্রদর্শন করে, যেসব ছবিতে সুনির্দিষ্টকোনো বস্তুর অবস্থান রয়েছে। আবার মাইক্রোসফট রিয়েল টাইমে ভাষান্তরের সফটওয়্যার প্রদর্শনকরে। কৃত্রিম বুদ্ধিমত্তা নিয়ে কাজ করছে এমন অনেক প্রতিষ্ঠান। প্রকৃতপক্ষে 'ডিপ লার্নিং'ক্রত্রিম বুদ্ধিমত্তাকে ভিন্ন একটি স্তরে পৌঁছে দিচ্ছে। যা সায়েন্স ফিকশনকে বাস্তবেপরিণত করতে সহায়তা করছে ।

 

ডিপ লার্নিং এর অ্যাপ্লিকেশনসমূহঃ

1.  সাদা ও কালো ছবির Colorization.
2.  ছবি থেকে বিভিন্ন অবজেক্ট চিহ্নিতকরন এবং ক্লাসিফিকেশন তৈরিকরা,
3.  ছবিতে ক্যাপশন জেনারেশন এবং চিহ্নিতকরন ,
4.  স্বয়ংক্রিয় হস্তাক্ষর জেনারেশন এবং চিহ্নিতকরন ,
5.  ক্যারেক্টার টেক্সট জেনারেশন এবং চিহ্নিতকরন ,
6.  নির্বাক চলচ্চিত্রের সাউন্ড যোগ করার পদ্ধতি .
7.  শব্দ থেকে টেক্সট জেনারেশন ,
8.  স্বয়ংক্রিয় মেশিন ট্রান্সলেসন.
9.  স্বয়ংক্রিয় গেম খেলা ,
10.  বিগ ডাটা এনালাইসিস ,
11.  আরও অন্যান্য চমকপ্রদ কিছু অ্যাপ্লিকেশন আছে । 

পাইথন কেন ব্যাবহার করবো? 

পাইথন , R এবং MATLAB এর ন্যায় পুর্নাংগ ফিচারসমৃদ্ধ জেনারেল পারপাস প্রোগ্রামিং ল্যাঙ্গুয়েজ । এটি দ্রুত এবং সহজ, এবং কোডলেখা অত্যন্ত সহজ এবং বুঝতে ঠিক সি++ এবং জাভার মত । পাইথনে রয়েছে সমৃদ্ধ অনেক লাইব্রেরী । যা দিয়ে ডিপ মেশিন লার্নিং এর ক্লাসিকাল এবং ফলিত কিছু অ্যাপ্লিকেশন খুব সহজেই ইমপ্লিমেন্টকরা যায় । এরকম কিছু  লাইব্রেরী হচ্ছেঃ 

 

#### 1. [Caffe](http://caffe.berkeleyvision.org/)

#### 2.  [Theano](http://deeplearning.net/software/theano/)

#### 3.  [TensorFlow](https://www.tensorflow.org/)

#### 4.  [Lasagne](https://github.com/Lasagne/Lasagne)

#### 5.  [Keras](http://keras.io/)

#### 6.  [mxnet](https://github.com/dmlc/mxnet)



আগামী পর্বে  আমরা কিভাবে ডিপ লার্নিং লাইব্রেরী  কিভাবে সেটআপ দেয়া যায় তা নিয়ে আলোচনা করবো । 



# ডিপ মেশিন লার্নিং এর জগতে আপনাদের স্বাগতম  :)