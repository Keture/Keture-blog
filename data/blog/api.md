---
title: API
date: '2022-03-14'
tags: ['API', 'REST', 'SOAP']
draft: false
summary: API - Application Programming Interface
authors: ['ben']
---

API - Application Programming Interface

**Hi! There, 😁**

If you are that person still looking for a better conclusion on topic API, I don't wanna pledge you that either you'll end up gaining a great knowledge or all your doubts regarding that will be resolved after reading this article, but definitely you'll end up learning something new. If you're kinda PRO, 🙌 point out me where I misinterpreted or 🙌 lemme know if anything is not within the bounds of the current topic.

# What exactly is API?

In simple terms, when two devices or applications needs to have a connection or talk to each other for sharing resources(data or functionalities) this is where API comes into the picture. If you want to integrate with Web APIs, you need to have a look on API documentation/specification of respective site . According to Wiki, [A document or standard that describes how to build such a connection or interface is called an _API specification_.](https://en.wikipedia.org/wiki/API#:~:text=A%20document%20or%20standard%20that%20describes%20how%20to%20build%20such%20a%20connection%20or%20interface%20is%20called%20an%20API%20specification.)
You may happen to see many times API Specification while browsing dev sites. Otherwise you have to dig little bit deeper to find this(not really 😉) out. Here are some decent API Documentation Examples FYI.

- [Stripe](https://stripe.com/docs/api)
- [Twillio](https://www.twilio.com/docs/usage/api)
- [GitHub](https://docs.github.com/en/rest/guides/getting-started-with-the-rest-api)
- [Spotify](https://developer.spotify.com/documentation/web-api/)

Wait....😑 What the heck is that Web API??? calm down Now let's take a look at the API types.

## API Types

According to the usage, It can be classified into 4 major types, those are,

1.  Web APIs - [Twitter API](https://developer.twitter.com/en/docs/twitter-api)
2.  Remote APIs - [Bazel API](https://bazel.build/)
3.  OS - [Windows API](https://docs.microsoft.com/en-us/windows/win32/apiindex/windows-api-list)
4.  Libraries & Frameworks - [Java API](https://docs.oracle.com/javase/7/docs/api/)

In this article we will focus mainly on web APIs, so we will quickly jump into Web APIs.

## Web APIs

Web APIs are enhancing your web app functionality and data. That means if you need to publish tweets of a particular person(Public Account) on your site. Now you need to interact with Twitter API for consuming this service. There are four principal types of API commonly used in web-based applications, So simply we can say 4 types of Web APIs.

1.  Public/Open Web APIs
2.  Private/Internal Web APIs
3.  Partner Web APIs
4.  Composite Web APIs

**1. Public/Open Web APIs**
The API is available to everyone. This allows third parties to develop apps that interact with your API and can be a source for innovation. [Spotify API](https://developer.spotify.com/)

**2. Private/Internal Web APIs**
The API is only for use internally. This gives companies the most control over their API.

**3. Partner Web APIs**
The API is shared with specific business partners. This can provide additional revenue streams without compromising quality. [Zoom API](https://marketplace.zoom.us/docs/api-reference/zoom-api)

**4. Composite Web APIs**
Composite APIs generally combine two or more APIs to craft a sequence of related or interdependent operations.

## API protocol(SOAP) and architecture(REST)

There are different approaches for different purposes. Web API techniques can be majorly divided into two types; data-driven & event-driven. Data-driven is called as REST/RESTful APIs and event-driven APIs are SOAP APIs. REST vs. RESTful comparison matter? Probably not. [Click here](https://blog.ndepend.com/rest-vs-restful/) If you want to know more about what Roy Fielding (The person who coined the word REST/RESTful) actually said.

1.  SOAP - Simple Object Access Protocol
2.  REST - REpresentational State Transfer architectural

The best analogy I've found on internet so as to illustrate the comparison between SOAP and REST.
![enter image description here](https://jelvix.com/wp-content/uploads/2020/09/app-server.jpg)
Hope you get it

|             | SOAP                                 | REST                                      |
| ----------- | ------------------------------------ | ----------------------------------------- |
| Style       | Protocol                             | Architectural                             |
| Function    | Event-driven                         | Data-driven                               |
| Data Format | Only XML                             | Plain Text, HTML, XML, JSON and so on     |
| Security    | WS-Security and SSL                  | SSL and HTTPS                             |
| Bandwidth   | Require more resources and bandwidth | Require more resources and is lightwieght |
| Data Cache  | Cannot be cached                     | Can be cached                             |

A SOAP Request

```xml
<?xml version="1.0"?>
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:xsd="http://www.w3.org/2001/XMLSchema"
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:cal="http://www.stgregorioschurchdc.org/Calendar">
<soapenv:Header/>
<soapenv:Body>
   <cal:easter_date soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
   <year xsi:type="xsd:short">2014</year>
</cal:easter_date>
</soapenv:Body>
</soapenv:Envelope>
```

As you can see here, Envelope tag has two childs; Header and Body. Header part will tell you the SOAP regualtions are maintained by W3C. SOAP is tightly coupled with the server; REST is coupled to a lesser degree. But SOAP is more secure than REST as it uses WS-Security for transmission along with Secure Socket Layer. Therefore choose wisely according to your application constraints & requirements.

A SOAP Response.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:xsd="http://www.w3.org/2001/XMLSchema"
SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
<SOAP-ENV:Body>
   <namesp1:easter_dateResponse
xmlns:namesp1="http://www.stgregorioschurchdc.org/Calendar">
<s-gensym3 xsi:type="xsd:string">2014/04/20</s-gensym3>
</namesp1:easter_dateResponse>
</SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

A JSON Request

```json
GET http://www.catechizeme.com/catechisms/catechism_for_young_children/daily_question.js HTTP/1.1
```

A JSON Response

```json
{
  "link": "catechisms/catechism_for_young_children/questions/36",
  "catechism": "Catechism for Young Children",
  "a": "Original sin.",
  "position": 36,
  "q": " What is that sinful nature which we inherit from Adam called?"
}
```

To be Continued 🎈🎈🎈
