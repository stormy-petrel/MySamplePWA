[Tutorial: Get started with Progressive Web Apps](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps-chromium/how-to/)


# Set up dev environment
- install Visual Studio Code 
- install node  `brew install node`
- clone the repo MySamplePWA
- run the web server locally: 
    - `npx http-server`  


# How to debug Service Worker

## Safari 
1. Open the Service Worker Inspector window:  `Safari`->`Develop`->`Service Worker` 
2. Print out what's in the cache in Console of Inspector Window
```javascript 
caches.open('cache-name').then(cache => {
     cache.keys()
     .then(requests => console.log(requests));
});
```
3. Go to the Web Inspector -> Network tab. After refreshing the page, Transfer Size column shows whether a file is loaded by Service Worker or the cache.   

4. Test with cache cleared then run the cache logging code in 2. again
```javascript
caches.open('cache-name')
  .then(cache => {
    cache.keys()
       .then(keys => {
             keys.forEach((request, index, array) => {
                 cache.delete(request)
        })
    })
  })
```
   
See details in [Debugging Service Workers in Safari](https://youtu.be/87RU7v6Y-bk?si=qwcP2ZUP98VuQEx_)

## Microsoft Edge 
See [Tutorial: Get started with Progressive Web Apps](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps-chromium/how-to/)