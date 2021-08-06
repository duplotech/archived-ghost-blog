---
title: How to install Keen IO Analytics into your Node.JS apps in mere seconds
slug: how-to-install-analytics-into-your-nodejs-apps-in-mere-seconds
date_published: 2014-03-05T07:38:00.000Z
date_updated: 2016-02-02T00:43:56.000Z
---

*This was written as [a guest blog post for Keen IO](https://keen.io/blog/78561215787/how-to-install-keen-io-analytics-into-your-node-js-app).*

*[Those that want to cut to the chase, should go and take a look at the project on Github here](https://github.com/sebinsua/express-keenio).*

**Have you ever found yourself putting off adding analytics until an app reaches its later stages of development and you're less busy?**

I think this is a mistake we all fall into all too often. In a highly competitive ecosystem, users will sometimes be with you on launch and gone the week after. By waiting too long, we can lose our one chance to study early user behaviour so it's very important that we take every opportunity we can to understand how they interact with the service while they're around.

But we also shouldn’t be wasting valuable development time installing analytics either. Surely installation should be a quick and simple process leaving you time free to work on the features that truly differentiate your product.

---

[Keen IO](http://keen.io) is an analytics platform for people that realise that off-the-shelf solutions often trap you into thinking about and analysing data in cookie-cutter ways, and that want an edge in *finding that one particular insight* that might make all the difference to a business.

**What if it were possible to future-proof your analytics needs, while also getting the benefits of quick and easy installation?**

I've made the [Express.JS middleware express-keenio](http://github.com/sebinsua/express-keenio) to help make this happen. 

Installation of analytics is now a 15-second process.

Just look how easy it is:

    var express = require("express"),  
        keenio = require('express-keenio').configure({ client: { projectId: '', writeKey: ''} });
    
    var app = express();
    
    app.post('/payments', keenio.trackRoute('payments',  { body: ['userId', 'itemId', 'type', 'quantity', 'price'], reaction: [] }), function (req, res) {  
      // Your code creating 'data' goes here.
      res.json(data);
    });
    
    app.listen(3000);  
    

A few lines of code, and your app (whether it's an MVP, a source of passive income, a side-project, or something you're making at a hackathon) will immediately begin capturing analytics data.

Later on, as your understanding and usage of analytics grows, an extensive configuration system allows you to adjust and restrict the middleware's behaviour however you please, with whitelists and blacklists, as well as options to control many other aspects of its operation. The Github [README](http://github.com/sebinsua/express-keenio) has everything you need to know.

---

**Philosophy**

If you’re not [defining events on an individual basis](https://keen.io/blog/53958349217/analytics-for-hackers-how-to-think-about-event-data), it’s helpful to come up with an underlying philosophy to event creation that holds true for a large number of user interactions.

My approach was to consider an event to be a crystallised interaction and describe it as [a mapping between an intention and a reaction](http://sebinsua.com/interfaces-as-loops), a rough analogue to an HTTP request and response. The only other information required to define useful events was coming up with some way of binding them to identities (metadata such as a user's IP address, or information such as email and username) and other forms of contextual environment metadata (such as the user agent.)

---

**The first release of [express-keenio can be found on Github here.](http://github.com/sebinsua/express-keenio)**

I welcome any feedback, issues to report, or pull requests you may have. It has been tested, but use some caution when installing it, as I can not guarantee that it is production-ready quite yet.

---

**[You should follow me on twitter here.](http://twitter.com/sebinsua)**
