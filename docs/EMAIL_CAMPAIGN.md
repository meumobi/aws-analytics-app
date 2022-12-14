Merry christmas

## Accessing event's attributes

On the web app front-end, I can trigger an event as follows:

```ts
await record("my.event", {
  attributes: { color: "red", size: "large" },
  immediate: true,
});
```

In Pinpoint, I can create a campaign with an email template to send an email to the user whenever my event is triggered. I'm able to access the endpoint attributes such as `{{User.UserAttributes.GivenName}}` or `{{Attributes.Preferences.Hats}}`.
