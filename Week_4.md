## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/server-side-app/schedule/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
> **Research and implement complex new features on our own**

>We decided to attempt to fulfil the "file upload" spike criteria, but rather than adding a file upload dialogue, we wanted the user to be able to draw an image on a canvas, then save that to the server. Luckily, it turned out there is a canvas method which returns the current contents of the canvas as a DataURL, which we were then able to process and store in the database:
```js
saveButton.addEventListener('click', () => {
  // Replace this with the URL of your Node.js server endpoint
  const endpoint = '/save';
  const dataURL = canvas.toDataURL('image/png');
  const base64Data = dataURL.replace(/^data:image\/png;base64,/, ''); // Remove data prefix

  ...

  //Save image fetch request
  fetch(endpoint, {
    method: 'POST',
    redirect: 'follow',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({ image: base64Data, caption: caption.value }),
  })
    .then((response) => {
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      if (response.redirected) {
        window.location.href = response.url;
      }
    })
    .catch((error) => {
      // Handle errors here
      console.error('There was a problem with the fetch operation:', error);
    });
});
```

 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> I didn't get a chance to work on implementing OAuth login this week, and it looks like a rather important technology to understand. Hopefully I'll revisit it soon.

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
