---
title: "Developers, Date APIs and Time zones"
datePublished: Wed Jan 10 2024 11:11:10 GMT+0000 (Coordinated Universal Time)
cuid: clr7ojvo500000al39z6ob2ju
slug: developers-date-apis-and-time-zones
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704872700980/0a5bc4e3-e675-46f4-88b3-db2b1ebcb6a8.jpeg
tags: programming-blogs, javascript, web-development, developer, datetime

---

Developers use `moment`, `Date` or other Date APIs depending upon their environment. But standard for the dates are provided by ISO to all the paradigms.

Recently, I was debugging my next unicorn SaaS (just kidding)  
I had some data in my MongoDB compass, which I'm writing below as `order` object.

```javascript
const order = {
  item: "SpaceX Starship",
  price: 1000000000,
  currency: "USD",
  deliveryDate: "2024-01-26T11:30:00.000+00:00",
  createdAt: "2024-01-23T20:30:00.637+00:00",
  updatedAt: "2024-01-23T20:30:00.637+00:00",
};
```

### Question is

At what time this order was **created** and at what time I'll get it **delivered**?

### Answer

The dates in `order` object are **ISO strings,** and since I'm in India, so I'm +5:30 hrs offset by **GMT.**  
So, I will add 5:30 hours to these dates, and I'll get these times in my local time, which is on **2024-01-24 2:00 AM** in the morning, I ordered the SpaceX Starship, and on **2024-01-26 5:00 PM**, I will receive the order.

> Greenwich Mean Time ( GMT ) also known as Coordinated Universal Time (UTC) are made universal by the ISO (the undisputed monarchy of standards, International Organization for Standardization )

### Why time zones exists?

If you've ever wondered, why don't we have a single time and why time zones add complexity by defining different times for different areas around the globe.

So here is a good news, we do have a single time and that is **Greenwich Mean Time ( GMT ) also known as Coordinated Universal Time (UTC),** accepted by ISO, and then who are we to reject!

**So, why time zones exists? or why do we different times for different zones around the globe?**  
Because of a simple reason that, just by looking at our clocks, we can confidently say that the sun is at its peak around 12:00 pm, rises approximately at 6 am, and sets around 5:30 pm during winters.

It also makes sense, when you think about the evolution of clocks, **clocks are just tracking the sun in the sky.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704872841619/fe1e39fc-cef8-48e7-976d-514e445da28e.png align="center")

( Right one is a sundial, ancestor of mechanical clocks, sundials are shadow clocks invented by ancient Egyptian and Babylonian astronomy around 1500 BC )

**Now that we understand the importance of the existence of time zones, lets understand how time zones works?**

Here is what humans did, first of all, they took a place **Greenwich, a town in London,** looked at its sundial time, and made it universal.

Then, they divided the globe and assigned an offset to each region, and asked people in that region to calculate their local time by adding or subtracting that offset from the **Greenwich time.**

Offsets are denoted as UTC+x or GMT+x, taking UTC or GMT as reference which are same thing. ( x is number of hours and +ve sign denotes you need to add it to the GMT time ).

If you're from India your offset is +5:30, UTC+5:30 or GMT+5:30, and you're timezone is known as "Asia/Kolkata".

Below is the map of the world, representing 24 timezone, and you can find city of Greenwich which lies in strip of 0 offset.

[![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704879786362/bb59f222-0d92-4097-bba8-372d5c37eded.jpeg align="center")](https://nationsgeo.com/time/timezonemap/UTC+6/)

### Lets code

If you have any package available in your development environment, which lets you format your date. you can do a simple experiment.

I'll be using `moment` package available in `npm Registry` .

```javascript
console.log(moment.tz("GMT").format("YYYY-MM-DD HH:mm:ss Z"));
// 2024-01-10 10:00:13 +00:00

console.log(moment.tz("Asia/Kolkata").format("YYYY-MM-DD HH:mm:ss Z"));
// 2024-01-10 15:30:13 +05:30
```

In the above code, you can see, first line prints standard **GMT or UTC time**, which is offset by 0 hours, of course

and second line prints India's local time which is offset by +5:30 hours.

### Conclusion

Thanks to the knowledge of time zone offsets, I can determine my local time by looking at an ISO date string like 2024-01-10T10:15:18.863Z. For example, this string translates to 15:45:18 on the 10th of January 2024 in India. Messaging software often stores dates in ISO strings, which can later be converted into local time, providing international communicators with information about when messages were delivered and received.