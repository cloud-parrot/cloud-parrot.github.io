---
layout: post
section-type: post
title: Creating an S3 Bucket For Kubernetes Cluster
category: tech
tags: [ 'tutorial' ]
---

All Kubernetes configuration will stored in S3 Bucket

<ol>
  <li>Use of mb command</li>
  <li>Naming the S3 bucket</li>
</ol>

Type the following command in your linux terminal:

<pre><code data-trim class="yaml">
aws s3 mb s3://S3_BUCKET_NAME
</code></pre>

S3 is the only object storage service that allows you to block public access to all of your objects at the bucket or the account level with S3 Block Public Access.

<small>Learn more about S3 Bucket on <a href="https://docs.aws.amazon.com/s3/index.html" target="\_blank">@joariasl</a> AWS official website!</small>
