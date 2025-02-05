# MultiCloud, DevOps & AI Challenge - Day 1  

```
[!TIP] 
Remember to use the class replay as a reference.  
```

## Streamlined Guide: Using Claude as AI Assistant to Terraform  

### Step 1: Use Claude to Generate Terraform Code  
1. Start a conversation with Claude.
2. Ask Claude to create Terraform code for an S3 bucket. Use a prompt like:
"Please provide Terraform code to create an S3 bucket in AWS with a unique name."
3. Claude should generate code similar to this:

```
provider "aws" {  
  region = "us-west-2"  # Replace with your desired    region  
}  
  
resource "random_id" "bucket_suffix" {  
  byte_length = 8  
}  
  
resource "aws_s3_bucket" "my_bucket" {  
  bucket = "my-unique-bucket-name-${random_id.  bucket_suffix.hex}"  

  tags = {  
    Name        = "My bucket"  
    Environment = "Dev"  
  }  
}  
  
resource "aws_s3_bucket_acl" "my_bucket_acl" {  
  bucket = aws_s3_bucket.my_bucket.id  
  acl    = "private"  
}  
  
```
4. Save this code for use in Step 5.  