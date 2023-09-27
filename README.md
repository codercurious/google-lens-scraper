# [Google lens scraper](https://apify.com/curious_coder/facebook-scraper)
## Sample data
Here are some examples of input images and corresponding output of the scraper:
### Reverse image search
This action finds websites with similar images and web pages containing matched image. You can use this feature when you want to search for variations of given image. 
For example, if you want to search for websites mentioning certain dog breeds, you can pass the dog photo url that breed and the scraper will return images from of that dog breed and their web page urls.
#### Input 
Lets pass a husky dog's image url that looks like this

![Reverse image search API input - Husky dog](https://cdn.britannica.com/84/232784-050-1769B477/Siberian-Husky-dog.jpg)

#### Scraper output
Here are 2 samples from the output of the scraper in JSON format. You can also get the output in other formats like CSV, XLS, etc

```json
[
	{
		"matchedImageLink": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS0dF2NyzBBKgA1HATtzEXqET4Q7Fl2G0j6ti5LW2S3fzJ4yo7R",
		"title": "25 Most Beautiful Dog Breeds - Bake Into",
		"link": "https://bakeinto.com/25-most-beautiful-dog-breeds",
		"websiteIcon": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS0dF2NyzBBKgA1HATtzEXqET4Q7Fl2G0j6ti5LW2S3fzJ4yo7R",
		"websiteName": "bakeinto.com",
		"givenUrl": "https://cdn.britannica.com/84/232784-050-1769B477/Siberian-Husky-dog.jpg"
	},
	{
		"matchedImageLink": "https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcT29smU4qFoAxvFxhczpV4FSEvIJRj3W6sut2jdUKKyt7R7BQmk",
		"title": "Pedigone Red Dog Body Cross with Black Lead 1.5-2m lengthy Harness & Leash Dog Belt.",
		"link": "https://www.amazon.in/Pedigone-Cross-1-5-2m-lengthy-Harness/dp/B082KPSJ8Q",
		"websiteIcon": "https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcT29smU4qFoAxvFxhczpV4FSEvIJRj3W6sut2jdUKKyt7R7BQmk",
		"websiteName": "Amazon.in",
		"givenUrl": "https://cdn.britannica.com/84/232784-050-1769B477/Siberian-Husky-dog.jpg"
	}
]
```
### Find image sources
This action finds web pages with given image. You can use this feature when you want to find most accurate matches. For example: If you want to find social media profiles of people by their profile pictures!

Let look at an example of how we can find websites mentioning elon musk

#### Input
Lets pass the url of image of elon musk's headshot photo: 

![Image match API input - Elon musk](https://imageio.forbes.com/specials-images/imageserve/62d700cd6094d2c180f269b9/0x0.jpg?format=jpg&crop=959,959,x0,y0,safe&height=416&width=416&fit=bounds)

#### Scraper output
Here are 2 samples from the output of the scraper in JSON format

```json
[
	{
		"title": "Forbes",
		"link": "https://www.forbes.com/profile/elon-musk/",
		"subtitle": "Forbes",
		"matchedImageLink": "https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcQqiDyK4zpIwrJSGjKzHY5GzVzcV3HbymcfiKxvGbRuWHdUQHxd",
		"websiteIcon": "https://encrypted-tbn2.gstatic.com/favicon-tbn?q=tbn:ANd9GcStsFTtOA-Gr2Cf1TGnVGGF1nqm10KGRhJS83fDnH-ZzYd8xji1iIzt-qzdIYjwIsySiHufTYXd2stTOLcrolb1witi-Zl1RkryuwGqDVGnyiorvQ",
		"websiteName": "Forbes",
		"givenUrl": "https://imageio.forbes.com/specials-images/imageserve/62d700cd6094d2c180f269b9/0x0.jpg?format=jpg&crop=959,959,x0,y0,safe&height=416&width=416&fit=bounds"
	},
	{
		"title": "Alux.com",
		"link": "https://www.alux.com/networth/elon-musk/",
		"subtitle": "Alux.com",
		"matchedImageLink": "https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcSRLbtUtEza35vd8CsbV7Y-aa4gLwVdOsRXvZfYrIh4iHgN1a1c",
		"websiteIcon": "https://encrypted-tbn2.gstatic.com/favicon-tbn?q=tbn:ANd9GcSL4xAYKXA5jhJ9G7LVZ71D6bL_LBSSlyiRquIhhB9S0Uo2A7CyFnX-0zgKWOjW0STkOTKRAqL5LN4KGSXdqU5RuASazkVpkyAhMeE66qs9Wyc",
		"websiteName": "Alux.com",
		"givenUrl": "https://imageio.forbes.com/specials-images/imageserve/62d700cd6094d2c180f269b9/0x0.jpg?format=jpg&crop=959,959,x0,y0,safe&height=416&width=416&fit=bounds"
	}
]
```

### Extract text from images (OCR)
You can use this feature when you want to perform OCR and extract text from images of documents or any image that has readable content. 

#### Input

![OCR API input - Image of a Document](https://images.template.net/wp-content/uploads/2016/07/26122540/Data-ware-Project-Documentation-Template.jpg)

#### Scraper output
Here is the output of the scraper in JSON format

```json
{
	"text": "Project Documentation\r\nThe Core Project Team has deemed the following project documents as required project artifacts for each phase of the project. These documents will be maintained during the project phases, and will be stored as project artifacts once the phase has been completed.\r\nScope Statement\r\nThis document defines the project scope determined by the Business Sponsor. This document should be reviewed and signed off by all team members so every one is aware of the project goal(s). This will be used to create the high-level project plan, data inventory list, report list and business requirements.\r\nDocument Name: Project Scope Statement\r\nData Inventory List\r\nThis is an excel spreadsheet that lists all of the data elements that are required to be brought over to Business Objects. The business creates this list based on the Scope Statement.\r\nNote: If there are more data elements added to BO that were not on the Data Inventory List, there needs to be a\r\nprocess in ensuring the Business is aware of these data elements.\r\nDocument Name: Data Inventory Template\r\nReport List\r\nThis is the list of reports that the business would like to produce in BO after the implementation\r\nThe business owner should list the names of the reports as well as provide electronic examples of each report. The business owner should also cross-reference all data elements in the reports to ensure they are captured in the Data Inventory List.\r\nDocument Name: Should be included in the Business Requirements and Data Inventory. There is no pre-defined template for this item. An annotated list with samples will suffice.\r\nBusiness Requirements\r\nThe business owner should specify WHAT they want in regards to the defined project scope. These include any specific use cases, or calculations. It details what the business owner expects the data will function in BO.\r\nNOTE: Once a security plan has been defined, the business requirements document needs to be updated to include a security section that defines the type of security required for the specific project.\r\nDocument Name: Data Warehouse Requirements Template",
	"givenUrl": "https://images.template.net/wp-content/uploads/2016/07/26122540/Data-ware-Project-Documentation-Template.jpg"
}
```
