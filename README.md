## TrueFootprint Technical Exercise

Thanks for considering TrueFootprint. The purpose of this exercise is to
establish whether you have the skills we need to build our software products.
We hope you find the exercise engaging and interesting and that it gives you an
indication of the kinds of problems you might solve working at TrueFootprint.

### How long should it take?

About an hour or two. You do not have to complete all steps if it takes longer
than that. We'd rather you take your time and make something good instead of
rushing to finish.

### Questions?

If something is unclear about the requirements of the exercise please email
[chris@truefootprint.com](mailto:chris@truefootprint.com). Hopefully that's not
necessary and we trust in your ability to make decisions for yourself.

### The exercise

The exercise is to create a minimal chat application that can work online or
offline, which is simulated by toggling a button. The following steps walk
through creating a simple backend and a React frontend that speaks to it. This
closely relates to one of our projects where users can collaborate to solve
problems when networking is not always available.

1. Create a web application in Ruby that will be our 'backend' and serve API
requests. Any choice of framework is fine, e.g. Rails, Rack, Grape, etc.

2. Create a page that runs React code. This can be part of the backend if you
wish or be a separate app. Any framework is fine, e.g. Next.Js, create-react-app, etc.

3. Create a 'Message' model in your backend with the following fields:

```
Message {
  body: Text,
  sender: String,
  posted_at: Timestamp,
}
```

You can use ActiveRecord if you wish and store messages in a database or you can
store them in Redis, write them to disk, etc. It's up to you. However, the
messages should persist when the application is restarted.

4. Create a `/messages` API endpoint that lists all messages as JSON, ordered
by the `posted_at` timestamp.

5. Make it so you can `POST` to `/messages` to create a new one. The server
should reject requests that do not contain all three fields.

6. Fetch the list of messages on page load and render it in your React app. They
should be formatted as 'sender: body', e.g. 'Alice: Hello, world!'

7. Add two text inputs to the page, one to enter your name and another to enter
the body of your message. Add a submit button that posts your message to the
backend.

8. Make it so your React app polls the `/messages` endpoint every 1 second and
re-renders the messages on the page.

8. Add another button that can be toggled to say 'Online' and 'Offline'.
When your app is online it should continue to poll and post new messages. When
your app is offline it should stop polling and stop posting messages to the backend.

9. Make it so that users can still submit messages while offline. Messages
 should be buffered and then sent one after another when the user goes back online.

### What's next?

Please zip up your code and email it to [chris@truefootprint.com](mailto:chris@truefootprint.com).
We'd rather you didn't make it public so that others can't use your submission.
It would be helpful if you included a brief paragraph about how you got on with
the exercise.

After that, we'll review the code and be in touch. Thanks for your time.
