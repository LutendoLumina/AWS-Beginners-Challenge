<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Lutendo Matshidze  
**Email:** lupreshie@gmail.com

---

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use S3 to host a static website. I'm doing this project to learn about AWS and cloud services and how they can be used to store objects in the cloud. (How does it work?)

### Tools and concepts

Services I used were Amazon S3. Key concepts I learnt include bucket policies, uploading static website files, index.html, bucket endpoint URLs and I also learnt about ACLs and how they control access to our bucket's objects.

### Project reflection

This project took me 1hr30 including demo time, quiz time and secret mission time. The most challenging part of the project was solving the 403 forbidden error. It was most rewarding to see the web page loading live and in public to the world.

---

## How I Set Up an S3 Bucket

Creating an S3 bucket took me less than 5 minutes. We needed to learn a few new concepts like block public access and ACLs but once all that was done we can create buckets in even shorter time in the future.

The Region I picked for my S3 bucket was Cape Town, because it the region that is closest to me. It is best practice to pick the region that is closest to you because it lowers time to retrieve your things (a.k.a latency).

S3 bucket names are globally unique! This means no two Amazon S3 buckets in the world can have the same name. Thry have to be completely unique regardless of the region and account ID.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### index.html and image assets

I uploaded two files to my S3 bucket - they were an index.html file, this determines the structure i.e on what goes inside your website and a folder of images and assets. This will fill in the website with images and things to look at.

Both files are necessary for this project as index.html determines the structure which does not illustrate the contents of the websites i.e If index.html says insert image here, it might not have the actual image to display hence the other files.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

Website hosting means putting our website files on the web server which is a computer designed to turn the files into a website page that people can visit.

To enable website hosting with my S3 bucket, I went to the properties tab of the bucket, enabled static hosting and also labled index.html as my index document i.e this is the document I'm trying to host.

An ACL (a.k.a Access Control List) is a way to configure permission settings inside a bucket. We enabled ACLs so that we can control access to our website files later.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

Once static website is enabled, S3 produces a bucket endpoint URL, which is an URL that takes you to the website that you and anyone can see on the internet.

When I first visited the bucket endpoint URL, I saw an error which 403 Forbidden. The reason for this error was objects in the bucket are public by default even though we have switched off local public access but the website files are still private.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

To resolve this 403 Forbidden error, I updated the access settings of the files inside the bucket. Using ACL , I made the files public.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

An alternative to ACLs are bucket policies, which are rules that determine who is allowed or not allowed to do something. The benefit of using bucket policies is you can have even greater control of the access of the actions that people are or are not allowed to do, while ACLs are useful for controlling public access for individual objects inside the bucket.

My bucket policy denies everyone from deleting our files in the bucket. I tested this by trying to delete index.html and saw a permission denied error. This means our bucket policy work. It successfully stopped us from deleting objects.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-host-a-website-on-s3_sm2sm2sm)

---

---
