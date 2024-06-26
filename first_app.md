# প্রথম অ্যাপস তৈরি

আমরা প্রোজেক্ট তৈরি করেছি, ডেভেলপমেন্ট সার্ভার রান করেছি, এখন অ্যাপ তৈরি করব! প্রথমেই ভার্চুয়াল এনভায়র্নমেন্ট একটিভ করুন এবং প্রোজেক্ট ফোল্ডারকে কারেন্ট ডিরেক্টরি করুন। এরপর এই কমান্ড দিনঃ

```text
python manage.py startapp myapp
```

প্রথম প্রজেক্ট তৈরি করার সময়ও আমরা এরকম একটা কমান্ড দিয়েছিলাম, তবে সেটা django-admin টুল ব্যবহার করে এবং এটা manage.py মডিউল ব্যবহার করে। এখানে অ্যাপ এর নাম দিয়েছি myapp আপনি যেকোন নাম দিতে পারেন। এখন আপনার প্রোজেক্ট ফোল্ডারে myapp নামে নতুন একটি ফোল্ডার তৈরি হবে, সেটাই অ্যাপ ফোল্ডার। ফোল্ডারটির ভিতরে কয়েকটি পাইথন ফাইল দেখতে পাবেন, সেগুলোঃ

![](https://i.imgur.com/m6F6JIP.png)

১\) migrations নামে একটি ফোল্ডার দেখবেন, ইগনোর করুন! 

২\) \_\_init_\_.py ফাঁকা ফাইল! myapp ফোল্ডারটিকে পাইথন প্যাকেজ বানানোর জন্য এই ফাইলটি তৈরি হয়েছে। 

৩\) admin.py এডমিন অ্যাপ সম্পর্কিত সেটিংসগুলো এখানে থাকবে, এডমিন বিষয়ে সামনে জানতে পারব! 

৪\) apps.py এই অ্যাপ স্পেসিফিক সেটিংস গুলো এই ফাইলে থাকবে। 

৫\) models.py মডেল এর কথা মনে আছেতো!? এমটিভি প্যাটার্নের মডেল। আপনার অ্যাপ এর সকল মডেল এই ফাইলে থাকবে। 

৬\) tests.py প্রাথমিক ভাবে জ্যাঙ্গোকে যতই কঠিন আর গোজামিল টাইপের মনে হোক না কেন, জ্যাঙ্গো আসলে খুবই অর্গানাইজড এবং বেস্ট প্র্যাকটিস ফলো করে তৈরি একটা ফ্রেমওয়ার্ক! তাই জ্যাঙ্গো সব সময় চায় যে তার \(ব্যবহারকারী\) ডেভেলপারগনও সবসময় বেস্ট প্র্যাকটিস ফলো করবে... আর কোড টেস্টিং বা ইউনিট টেস্টিং হল বেস্ট প্র্যাকটিসের অন্যতম একটা অংশ! ইউনিট টেস্ট বা টেস্টিং কোডগুলো লেখার জন্য জ্যাঙ্গো অটোমেটিক আপনার জন্য এই ফাইল তৈরি করে দেয়!!! 

৭\) views.py ভিউ, আপনার ওয়েবসাইটের কেন্দ্রবিন্দু... এই ফাইলেই সকল ভিউ তৈরি করা হবে!

আমাদের প্রথম অ্যাপ তৈরি হয়ে গেছে, কিন্তু এটা এখনো আমাদের প্রোজেক্টে ব্যবহারযোগ্য হয়ে উঠেনি! আপনি কি বলতে পারবেন কেন?


