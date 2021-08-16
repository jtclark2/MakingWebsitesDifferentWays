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
