---
layout: post
title:উবুন্টু ১৬.০৪ এ ডিপ লার্নিং লাইব্রেরী ইন্সটল 
subtitle:
published: true
---


### ডিপ লার্নিং এনভাইরনমেন্ট তৈরি

ইমেজ প্রসেসিং এবং ক্লাসিফিকেশন  , নিউরাল নেটওয়ার্ক (NN) , কনভলুসনাল নিউরাল নেটওয়ার্ক (CNN) , রি-ওকারেন্ট  নিউরাল নেটওয়ার্ক (RNN) ,  LSTM প্রভৃতি ইমপ্লিমেন্টেশন করার জন্য আমাদের একটা এনভাইরনমেন্ট তৈরি করতে হবে যেখানে আমরা নিম্নোক্ত উপায়ে সেটআপ করতে পারি ,



### Python Virtual Environment

প্রথমেই pip ইউজ করে  ভার্চুয়াল এনভাইরনমেন্ট ইন্সটল করতে হবে  [(see, e.g., this site)](http://docs.python-guide.org/en/latest/dev/virtualenvs/). আমি  Python 2.7 ভার্সন ইউজ করেছি  কেননা এটা সবচেয়ে স্টাবল । 

```
$ pip install virtualenv
```

অতঃপর আমি ` venv` নামে একটি ভার্চুয়াল এনভাইরনমেন্ট ডিরেক্টরি তৈরি করে নিয়েছি  নিচের কমান্ড টি দ্বারা  

```
$ virtualenv venv
```

ডিরেক্টরি তৈরি করার পর সেটিকে আক্টিভেট করে নিলাম

```
$ source ./venv/bin/activate 
```

যখন  আক্টিভেট করা শেষ তখন ডি-এক্টিভেট করে নিলাম  

```
$ deactivate
```

### TensorFlow

আমরা এখন [TensorFlow](https://www.tensorflow.org/) এর ভার্সন  0.11 ইউজ করছি (বিস্তারিত পাবো [এখনে ](https://www.tensorflow.org/versions/r0.11/get_started/os_setup.html#virtualenv-installation))  আমার ক্ষেত্রে আমি পুনরায়  ` venv` activate করেছি নিচের কমান্ডটি দিয়ে :

```
# Ubuntu/Linux 64-bit, CPU only, Python 2.7
(venv)$ export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0rc0-cp27-none-linux_x86_64.whl
(venv)$ pip install --upgrade $TF_BINARY_URL
```

এখন আমি  `import tensorflow` দিয়ে  virtual environment এ ` tensorflow `  ইমপোর্ট করতে সক্ষম হয়েছি । 

### Keras

আমরা এখন [Keras](https://keras.io/) 1.1.0 ([github link](https://github.com/fchollet/keras)).  এখানেই ইন্সটল করবো :

```
(venv)$ pip install --upgrade git+https://github.com/fchollet/keras.git
```

এছাড়াও আমি  `~/.keras`  এ ` keras.json`  নামে একটি ফাইলে নিচের কোডটুকু `~/.keras/keras.json` নিশ্চিত করবো  

```
{
  "image_dim_ordering": "tf",
  "epsilon": 1e-07,
  "floatx": "float32",
  "backend": "tensorflow"
}
```

### OpenCV and Linux

 Ubuntu তে   OpenCV আর  python  `cv2` কনফিগার করা একটু জটিল . আমি নিচের পদ্ধতিতে করেছি :

-   OpenCV আর  python bindings ইন্সটল  করার জন্য ( virtual environment নয় কিন্তু )

```
$ sudo apt-get install libopencv-dev python-opencv
```

-   Symlink `cv2` to your virtual environment's site packages.

```
$ cd /path/to/venv/lib/python2.7/site-packages/
# For Ubuntu:
$ ln -s /usr/lib/python2.7/dist-packages/cv2.x86_64-linux-gnu.so cv2.so
```

লক্ষ্য করুন , আমার ক্ষেত্রে Ubuntu  16.04 এ  এমন ছিল 

`cv2.x86_64-linux-gnu.so`  কিন্তু আপনার ক্ষেত্রে ভিন্নও থাকতে পারে তাই    এভাবে খুজতে পারেন ,

`ls /usr/lib/python2.7/dist-packages/cv2*`.



আজ এ পর্যন্তই রইলো ,  আপনার ডিপ লার্নিং শুভ হোক । 
