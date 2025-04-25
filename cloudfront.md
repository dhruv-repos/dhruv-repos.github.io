---
title: AWS Cloudfront
layout: default
---
# AWS Cloudformation
Summary & Explanation of CloudFront Points of Presence (POPs) and Regional Edge Caches

1. CloudFront POPs (Edge Locations)
These are global locations where Amazon CloudFront caches popular content.
Their purpose is to serve frequently requested content quickly to users by reducing latency.
2. Regional Edge Caches
These sit between CloudFront's POPs and the origin server.
They store content that is not popular enough to stay in a POP but still needs to be closer to users.
Since regional edge caches have larger storage than POPs, they retain less frequently accessed objects for longer.
This reduces the number of requests going back to the origin server, improving performance.
> How Requests Flow Through CloudFront
    1. A user requests content via a website or app.
    2. DNS directs the request to the nearest CloudFront POP (edge location).
    3. The POP checks if it has the content cached:
    If cached, it serves the content directly.
    If not cached, it fetches the content from the nearest regional edge cache.
    4. If the content is also not in the regional edge cache, CloudFront fetches it from the origin server (e.g., an S3 bucket or web server).
    5. The content is then:
    Stored in the regional edge cache (for future requests).
    Stored in the POP (for quick access).
    Sent to the user.
4. Key Behaviors & Features
Cache Invalidation: Deleting a cached object removes it from both POPs and regional edge caches.
Dynamic Requests (e.g., API calls, user-specific content): These requests skip the regional edge caches and go straight to the origin.
Proxy HTTP Methods (PUT, POST, PATCH, OPTIONS, DELETE): These also bypass regional edge caches and go directly to the origin.
Amazon S3 Optimization: If a requested object is stored in an S3 bucket within the same AWS region, the request skips the regional edge cache and goes straight to S3.


Why This Matters
Faster Content Delivery: Keeping content closer to users improves load times.
Reduced Origin Load: Fewer direct requests to the origin reduce server costs and improve efficiency.
Better Handling of Changing Content Popularity: Even as content demand fluctuates, CloudFront ensures it’s stored in the best location to optimize speed and cost.


## Distribution Console options
> What can be a origin ?
> 1. Amazon S3 bucket .s3
> 2. S3 bucket as a website .s3-website
> 3. MediaStore container  .data.mediastore
> 4. MediaPackage endpoint .mediapackage
> 5. EC2 instance .compute-1.
> 6. Elastice Load Balancing load balancer  .elb.
> 7. Own Web Server  www.example.com

- **Origin Domain** : The DNS domain name of the resource where CloudFront will get objects for your origin 

Content delivery 
what is cloud front
edge vs regional
distribution console options
invalidation
ui options
logging
security options and origins 
error pages and configure behaviour per page
continuous deployment
SSL certificate 



## Secure Sockets Layer 
SSL is an encryption based internet security protocol
