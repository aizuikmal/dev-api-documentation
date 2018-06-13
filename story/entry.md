---
description: 'This endpoint to retrieve, post and delete story.'
---

# /entry

{% api-method method="get" host="https://api.newscraft.io/v1" path="/story/entry" %}
{% api-method-summary %}
Get stories
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get entry.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=true %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}
API key provided by platform provider.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
The entry ID provided by system. 32-char
{% endapi-method-parameter %}

{% api-method-parameter name="sid" type="string" required=false %}
Custom ID which stored during POST
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" required=false %}
Default, limit is 50 \(maximum\)
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
Default, start from 0
{% endapi-method-parameter %}

{% api-method-parameter name="feed\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="cat\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="lang\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="author\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="sort" type="string" required=false %}
Default, date\_pub. Possible value: date\_pub, date\_mode, title
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_desc" type="boolean" required=false %}
If true, the sort is descending. If false, sort is ascending.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.newscraft.io/v1" path="/story/entry/:id" %}
{% api-method-summary %}
Get single story
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=true %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}
API key provided by platform provider.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="string" required=false %}
The entry ID provided by system. 32-char
{% endapi-method-parameter %}

{% api-method-parameter name="sid" type="string" required=false %}
Custom ID which stored during POST
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" required=false %}
Default, limit is 50 \(maximum\)
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
Default, start from 0
{% endapi-method-parameter %}

{% api-method-parameter name="feed\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="cat\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="lang\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="author\_id" type="string" required=false %}
32-char
{% endapi-method-parameter %}

{% api-method-parameter name="sort" type="string" required=false %}
Default, date\_pub. Possible value: date\_pub, date\_mode, title
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_desc" type="boolean" required=false %}
If true, the sort is descending. If false, sort is ascending.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.newscraft.io/v1" path="/story/entry" %}
{% api-method-summary %}
Post new story
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=true %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

POST with JSON body

```javascript
{  
   "sid":"999999",
   "title":"Full title of the story",
   "title_alt":"Alternate title",
   "feed_id":["xxxx","yyyy"], //array of feed id
   "cat_id":["xxxx","yyyy"], //array of category id
   "cat_str":["news","letters"], //array of category name
   "author_id":["xxxx","yyyy"], //array of author id
   "author_str":["Jim","Terry"], //array of author name
   "lang_id":["xxxx","yyyy"], //array of lang id
   "lang_str":["en"], //array of lang code
   "source":"CNN",
   "summary":"Summary for the story ",
   "date_pub":1528552260,
   "date_mod":1528552668,
   "user_pub":"xxxxxx", //User ID which publish this story
   "user_mod":"xxxxxx", //User ID which modify this story
   "status":"published",
   "image_feat":["http://i.image.com/1.jpg","http://i.image.com/2.jpg"],
   "content":"<p>Lorem ipsum dolor sit amet</p><p>Ad cum graeci nostrum.</p>"
}
```

{% api-method method="post" host="https://api.newscraft.io/v1" path="/story/entry/:id" %}
{% api-method-summary %}
Edit existing story
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=true %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

POST with JSON body

```javascript
{  
   "sid":"999999",
   "title":"Full title of the story",
   "title_alt":"Alternate title",
   "feed_id":["xxxx","yyyy"], //array of feed id
   "cat_id":["xxxx","yyyy"], //array of category id
   "cat_str":["news","letters"], //array of category name
   "author_id":["xxxx","yyyy"], //array of author id
   "author_str":["Jim","Terry"], //array of author name
   "lang_id":["xxxx","yyyy"], //array of lang id
   "lang_str":["en"], //array of lang code
   "source":"CNN",
   "summary":"Summary for the story ",
   "date_pub":1528552260,
   "date_mod":1528552668,
   "user_pub":"xxxxxx", //User ID which publish this story
   "user_mod":"xxxxxx", //User ID which modify this story
   "status":"published",
   "image_feat":["http://i.image.com/1.jpg","http://i.image.com/2.jpg"],
   "content":"<p>Lorem ipsum dolor sit amet</p><p>Ad cum graeci nostrum.</p>"
}
```

{% api-method method="delete" host="https://api.newscraft.io/v1" path="/story/entry/:id" %}
{% api-method-summary %}
Delete single story
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=false %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.newscraft.io/v1" path="/story/entry/:id/autosave" %}
{% api-method-summary %}
Post autosave
{% endapi-method-summary %}

{% api-method-description %}
This endpoint is for WYSIWYG HTML editor to post autosave to backend, and update the content for specific entry ID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=true %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Will only receive HTML body content.

```markup
<p>This is updated content.</p>
```

{% api-method method="get" host="https://api.newscraft.io/v1" path="/story/entry/:id/rev" %}
{% api-method-summary %}
Get story revisions
{% endapi-method-summary %}

{% api-method-description %}
Get list of story revisions.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=false %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.newscraft.io/v1" path="/story/entry/:id/rev" %}
{% api-method-summary %}
Restore story content from revision
{% endapi-method-summary %}

{% api-method-description %}
This action will copy content from revision's copy into entry's content field. The restore action also will update a new revision entry and will be logged.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=false %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="rev\_id" type="string" required=true %}
The revision ID to restore from \(32-char\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.newscraft.io/v1" path="/story/entry/:id/content" %}
{% api-method-summary %}
Get full content
{% endapi-method-summary %}

{% api-method-description %}
This full content is intended to be use for WYSIWYG pre-filled. Also, can be use for content processing by other microservices. Not for front-end.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Entry ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="x-pub-id" type="string" required=true %}
Publisher ID
{% endapi-method-parameter %}

{% api-method-parameter name="x-api-key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
