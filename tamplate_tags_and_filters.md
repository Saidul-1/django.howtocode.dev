# টেমপ্লেট ট্যাগ এবং ফিল্টার

জ্যাঙ্গো টেমপ্লেট ল্যাঙ্গুয়েজ \(DTL\) একদম এইচটিএমএল এর মতই! তবে তাতে অতিরিক্ত কিছু সুবিধা পাওয়া যায়! উল্লেখযোগ্য সুবিধাগুলো হলঃ

১\) টেমপ্লেট ইনহেরিটেন্স! পাইথনে আমরা যেভাবে এক ক্লাস থেকে আরেক ক্লাস কে ইনহেরিট করি, টেমপ্লেট ল্যাঙ্গুয়েজেও সেরকমটা করা যায়, একটা বেজ টেমপ্লেট তৈরি করে সেটা যেকোনো চাইল্ড টেমপ্লেটে ইনহেরিট করে নেয়া যায়!

২\) টেমপ্লেট ইনক্লুডিং! যদি টেমপ্লেট বড় হয়ে যায় সেটাকে আমরা বিভিন্ন ফাইলে বিভক্ত করে যেকোন একফাইলে ইনক্লুড করে নিতে পারি! উদাহরণস্বরূপ, আমরা টেমপ্লেট এর হেডার, ফুটার, সাইডবার, ন্যাভম্যানু বার, স্লাইডার ইত্যাদি আলাদা আলাদা ফাইলে লিখতে পারি এবং সেগুলোকে হোম পেইজ বা অন্য কোন পেইজে ইনক্লুড করে দিতে পারি। এতে বারবার কোড করা থেকে মুক্তি পাওয়া যাবে এবং কোড ওয়েল অর্গানাইজড থাকবে।

> টেমপ্লেট ইনক্লুড করা এবং টেমপ্লেট ইনহেরিট করা নিয়ে প্রথম প্রথম কনফিউশন লাগতে পারে, দুটোকে প্রায় এক মনে হলেও তাদের মধ্যে কিন্তু অনেক পার্থক্য আছে!

৩\) টেমপ্লেট ট্যাগ ব্যবহার! ট্যাগ এর মাধ্যমে আমরা পাইথনের কমন কিছু ফাংশনালিটি সরাসরি টেমপ্লেটেই ব্যবহার করতে পারি! যেমন ইফ/এলস কন্ডিশন চেক করা, ফরলুপ চালানো, ফাংশন কল করা, ভেরিয়েবল কল করা ইত্যাদি বিষয়গুলো ট্যাগ দিয়ে করা যায়!

৪\) টেমপ্লেট ফিল্টার! এটাকে পাইথনের ফাংশন বা মেথডের সাথে তুলনা করা যায়, ফিল্টার মুলত টেমপ্লেট ট্যাগের উপর ব্যবহার করা হয় সেই ট্যাগের ভ্যালুতে নির্দিষ্ট কিছু পরিবর্তন করার জন্য। যেমন কোনো স্ট্রিংকে আপারকেস করা, ডেটটাইমকে হিউম্যান রিডেবল করা, কোন টেমপ্লেট ট্যাগ এর ডিফল্ট মান দেয়া ইত্যাদি কাজ গুলো ফিল্টার দিয়ে করা যায়।

আগের চ্যাপ্টারে ভিউ থেকে আমরা একটি ভেরিয়েবলকে টেমপ্লেটে পাস করেছিলাম যেটা messages ‘কী’ এর মাধ্যমে এক্সেস করা যাবে, সে ভেরিয়েবল এর ভ্যালুগুলো এখন আমরা টেমপ্লেট ট্যাগ এর মাধ্যমে শো করব।

Myapp এপ এর ভিতরের templates ফোল্ডারে থাকা index.html ফাইলটি ওপেন করুন \(ডিরেক্টরিঃ `myproject\myapp\templates` \), সেটার কোডগুলো এরকম ছিলঃ

```text
<!DOCTYPE html>
<html>
    <head>
        <title>My view</title>
    <head>
    <body>
        <h1>Hello World!</h1>
    </body>
<html>
```

এখানে `<h1>Hello World!</h1>` এর নিচে লিখুনঃ

```text
{% for message in messages %}
    <p> {{ message.text }} </p>
{% endfor %}
```

খেয়াল করে দেখুন, এটা কিন্তু একটা ফরলুপ! পাইথনের ফরলুপের মতই, শুধু দুটি পার্থক্যঃ ১\) ফরলুপটিকে আমরা \`

`এরকম বন্ধনির ভিতর রেখেছি! এটা হল ট্যামপ্লেট ট্যাগে এর সিন্ট্যাক্স, ফরলুপ, ফাংশন কল, কন্ডিশন চেক ইত্যাদি কাজগুলো করতে হলে সেগুলোকে এই বন্ধনির ভিতর রাখতে হবে। ২) তিন নাম্বার লাইনে দেখুন`

\` ট্যাগ দিয়ে আমরা ফরলুপ ব্লক এর শেষ বুঝিয়েছি, পাইথনে যেমন ইন্ডেন্টেশন ব্লক দিয়ে ফরলুপ বা অন্যান্য কোড ব্লগ বোঝানো হয়, ট্যামপ্লেট ল্যাঙ্গুয়েজে যেহেতু ইন্ডেন্টেশন বাধ্যতামুলক নয় তাই এখানে স্পষ্ট ভাবে কোডব্লক এর শেষ উল্লেখ করে দিতে হবে!

মধ্যবর্তি লাইনটাতে এইচটিএমএল এর `<p> </p>` ট্যাগে এর ভিতর `{{ message.text }}` লিখে আমরা `message` এর `text` ফিল্ডকে কল করছি। এটা ট্যামপ্লেট ট্যাগ এর আরেক সিন্ট্যাক্স, কোন ধরনের ভেরিয়েবলকে কল করতে চাইলে `{{ }}` এরকম বন্ধনির ভিতর তা লিখতে হবে!

তো আমাদের `index.html` ফাইলের সম্পুর্ন কোডটি এখন এরকমঃ

```text
<!DOCTYPE html>
<html>
    <head>
        <title>My view</title>
    <head>
    <body>
        <h1>Hello World!</h1>

        {% for message in messages %}
            <p> {{message.text}} </p>
        {% endfor %}

    </body>
<html>
```

এখন কমান্ড লাইন থেকে আবার ডেভেলপমেন্ট সার্ভার চালু করুন এবং ব্রাউজারে এই ঠিকানায় যানঃ

```text
http://127.0.0.1:8000/myview/
```

দেখবেন আমাদের তৈরি করা তিনটি মেসেজ সুন্দর ভাবে শো করছেঃ

![](https://i.imgur.com/osyfgeM.png)

> **এক নজরেঃ** যখনই আমরা ব্রাউজেরে `http://127.0.0.1:8000/myview/` ইউআরএল লিখে এন্টার চাপছি তখন ব্রাউজার আমাদের সার্ভারে একটা রিকুয়েস্ট পাঠাচ্ছে, তারপর আমাদের সার্ভারে থাকা জ্যাঙ্গো সেই ইউআরএল টাকে `urls.py` ফাইলে থাকা ইউআরএল গুলোর সাথে মিলিয়ে দেখছে যে এই ইউআরএল এর সাথে সংযুক্ত কোন ভিউ আছে কিনা! যখন সে এটার সাথে `index()` ভিউ এর ম্যাচ পেল সাথে সাথে `index()` ভিউকে কল করল। `index()` ভিউ প্রথমে `Message` মডেলের অবজেক্টগুলোকে নিয়ে আসল এবং সেটাকে ট্যামপ্লেট এর মাধ্যে রেন্ডার করতে দিল, ট্যামপ্লেটে অবজেক্টগুলো ঠিক মত রেন্ডার হয়ে গেলে `index()` ভিউটি সেটাকে রেসপন্স হিসেবে ব্রাউজারে পাঠিয়ে দিল আর আমরা ব্রাউজের আমাদের কাঙ্ক্ষিত ফলাফল দেখতে পেলাম!
