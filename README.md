# Actor - ImageShack Scraper

## ImageShack scraper

Since ImageShack doesn't provide a good and free API, this actor should help you to retrieve data from it.

The ImageShack data scraper supports the following features:

-   Retrieve Stunning Images from ImageShack - Explore an efficient way to gather captivating images from ImageShack using our advanced scraping tool. Extract image id, links, tags, usernames, and more with lightning speed.

-   Stay Updated with Featured Images - Stay ahead by accessing a curated collection of featured images from ImageShack. Our scraper empowers you to effortlessly retrieve images that have been highlighted by ImageShack, keeping you informed and inspired.

-   Discover the Latest on the Discover Page - Dive into the world of ImageShack's discover page with real-time scraping. Our tool enables you to stay up-to-date by extracting images directly from the discover page, ensuring you're always in the loop.

-   Effortlessly Fetch Image Data - Experience the ease of retrieving image data with our streamlined scraping solution. Fetch image details such as IDs, links, usernames, tags, and more at an astonishing pace, empowering your data-driven projects.

-   Unlock Related Images at Your Fingertips - Uncover a wealth of related images provided by ImageShack effortlessly. Our scraper allows you to access and explore a plethora of images that are interconnected, expanding your creative and research horizons.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/imageshack-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on ImageShack that should be visited. Required fields are:

- `startUrls`: (Optional) (Array) List of ImageShack URLs. You should only provide a news list, jobs list, or detail URLs.

- `includeRelatedImages`: (Optional) (Boolean) This will add all the related images that ImageShack provides into the image objects. Please keep in mind that the time and resources the actor uses will increase proportionally to the number of related images.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detailed requests. If the actor doesn't block very often it'll scrape 100 listings in 1 minutes with ~0.01-0.03 compute units.

### ImageShack Scraper Input example

```json
{
  "startUrls":[
    "https://imageshack.com/featured",
    "https://imageshack.com/i/f0e2aa72j",
    "https://imageshack.com/user/AndrewMcCall",
    "https://imageshack.com/discover"
  ],
  "includeRelatedImages":false,
  "maxItems":20,
  "proxy":{
    "useApifyProxy":true
  }
}

```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## ImageShack Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this ImageShack actor.

## Scraped ImageShack Properties

The structure of each item in ImageShack looks like this:

### Item Detail

```json
{
	"type": "image",
	"url": "https://imageshack.com/i/f0e2aa72j",
	"imageId": "f0e2aa72j",
	"imageUrl": "http://imageshack.com/scaled/medium/540/e2aa72.jpg",
	"imageUrlAlt": "https://imagizer.imageshack.com/a/img540/1851/e2aa72.jpg",
	"imageName": ".",
	"userAvatar": "https://imagizer.imageshack.com/v2/56x56q70/c/843/0f7u.jpg",
	"tags": [
		"bike",
		"game",
		"jump",
		"photography",
		"sport",
		"sports"
	],
	"uploadedAt": "2014-07-16 11:18",
	"relatedImages": []
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
