# Collect analytics

[Analytics Auto Tracking](https://docs.amplify.aws/lib/analytics/autotrack/q/platform/js/) helps to automatically track user behaviors like sessions start/stop, page view change and web events like clicking, mouseover.

## Session tracking

A web session can be defined in different ways. To keep it simple we define that the web session is active when the page is not hidden and inactive when the page is hidden.

```ts
Analytics.autoTrack("session", {
  // REQUIRED, turn on/off the auto tracking
  enable: true,
  // OPTIONAL, the attributes of the event, you can either pass an object or a function
  // which allows you to define dynamic attributes
  attributes: {
    attr: "attr",
  },
  // when using function
  // attributes: () => {
  //    const attr = somewhere();
  //    return {
  //        myAttr: attr
  //    }
  // },
  // OPTIONAL, the service provider, by default is the Amazon Pinpoint
  provider: "AWSPinpoint",
});
```

### Page view tracking

```ts
Analytics.autoTrack("pageView", {
  // REQUIRED, turn on/off the auto tracking
  enable: true,
  // OPTIONAL, the event name, by default is 'pageView'
  eventName: "pageView",
  // OPTIONAL, the attributes of the event, you can either pass an object or a function
  // which allows you to define dynamic attributes
  attributes: {
    attr: "attr",
  },
  // when using function
  // attributes: () => {
  //    const attr = somewhere();
  //    return {
  //        myAttr: attr
  //    }
  // },
  // OPTIONAL, by default is 'multiPageApp'
  // you need to change it to 'SPA' if your app is a single-page app like React
  type: "multiPageApp",
  // OPTIONAL, the service provider, by default is the Amazon Pinpoint
  provider: "AWSPinpoint",
  // OPTIONAL, to get the current page url
  getUrl: () => {
    // the default function
    return window.location.origin + window.location.pathname;
  },
});
```

## Custom events

```js
Analytics.record({
  name: "stackView",
  attributes: {}, // OPTIONAL
  metrics: { clipsWatched: 3 }, // OPTIONAL
});
```

## Default analytics events

| Event name           | Description                                                                                                                                        |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| \_session.start      | The endpoint began a new session                                                                                                                   |
| \_session.stop       | The endpoint ended a session                                                                                                                       |
| \_userauth.sign_in   | The endpoint logged in to your app                                                                                                                 |
| \_userauth.sign_up   | A new endpoint completed the registration process in your app                                                                                      |
| \_userauth.auth_fail | The endpoint attempted to sign in to your app, but wasn't able to complete the process                                                             |
| \_session.pause      | The endpoint paused a session. Paused sessions can be resumed so that you can continue to collect metrics without starting an entirely new session |

[Source: AWS guide/App events](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-app.html)
