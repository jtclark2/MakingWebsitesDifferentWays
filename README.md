# MakingWebsitesDifferentWays
Trivial Sites that will be used to test various deployment approaches

## Method 1: Deploy Static Websites (using Amazon S3)
- Go to S3 service
- Create bucket (make sure to enable public access)
- Configure Bucket
    - Properties → Static website hosting → edit → enable 
        - Use all the defaults
        - For this example
            - The default (index document) page is `index.html`
            - The error document is `error.html`...though I don’t think we’ll use it
    - Permissions → Edit bucket policy
        - Paste in example, swapping in your own bucket name (leaving the trailing `/*`, to indicate this applies to everything in that bucket)
    - Objects → Upload → index.html
        - Use defaults for upload
        - index.html is just a simple hello world written in html
- Go back to properties → Static website hosting
    - Follow the link to see the contents of `index.html` being displayed

## Method 2: Deploy Serverless (AWS Lambda)
1) Create Lambda Function
    1) Open Lambda service (he has this option directly in cloud9, but it’s either a plugin, or there has been a GUI change since he filmed 
    2) Create Function:
        1) Select Function name
        2) Select runtime (eg: python)
    3) Configure Lambda Function
        1) Function overview → +Add Trigger
            1) For this example, select API, which is used for http and RESTful APIs
                1) Select REST
        2) Security: Select Open, so that no additional configuration is required yet
    4) Create content for the function (see lambda_function.py)
2) Test Lambda Function:
    1) Create Test Event
        1) Provide input keys and values (`{“key”: “value”}`), or just use open braces `{}` for now
    2) Deploy
    3) Test: 
        1) Make sure to `deploy` before testing
        2) You should see 
3) View content:
    1) Select the API Gateway trigger that you created above
    2) Go to details, and follow the link to `API endpoint`
        1) You should seen the content returned from your function call
