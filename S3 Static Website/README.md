📜 Step-by-Step Instructions
Here’s how to host your static website on AWS S3:

1. Log in to AWS Console
Access the AWS console.
Search for S3 in the top search bar and select it.
2. Create an S3 Bucket
Click on Create bucket.
Enter a unique Bucket name for your website.
3. Adjust Bucket Settings
Uncheck Block all public access to make your website publicly accessible.
Click Create bucket.
4. Select Your Bucket
Locate your newly created bucket and click on it.
5. Enable Static Website Hosting
Go to the Properties tab.
Scroll to Static website hosting and click Edit.
Enable hosting and specify your website's index document (e.g., index.html).
6. Add Optional Error Handling
Optionally, specify an error document (e.g., error.html) to display when a file is not found.
Save the changes.
7. Get Your Website Endpoint
Enabling Static website hosting generates a unique bucket endpoint URL for your site.
8. Set a Bucket Policy
Allow public access to your website files.
Under the Permissions tab, locate the Bucket policy section.
Add a policy that grants read access, replacing <your-bucket-ARN> with your bucket's ARN:
json
Copy
Edit
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<your-bucket-name>/*"
    }
  ]
}
9. Upload Website Files
Upload all website files to your bucket, ensuring your index.html is present.
10. Finalize and Test
Navigate to the Properties tab and access your bucket's endpoint.
Your index.html file will load as the home page.
If there’s an issue (e.g., missing index file), the specified error document will appear.
📄 Example Files
Here are the key files for your static site:

index.html: The main page of your website.
error.html: A custom error page for handling missing resources.
