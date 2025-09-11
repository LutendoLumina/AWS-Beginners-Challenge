<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** Lutendo Matshidze  
**Email:** lupreshie@gmail.com

---

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use AWS IAM to control access and permission settings in my AWS account. I'm doing this project to learn about Cloud Security from the absolute basics and foundations - every company thinks about access permissions and there are even entire jobs called 'IAM Engineers' focused on the skills we're about to build today.

### Tools and concepts

Services I used were Amazon EC2 and AWS IAM. Key concepts I learnt include IAM users, policies, user groups and account aliases. I also learned how to use Policy Simulator and how JSON policies work and also how to launch an instance , how to tag an instance, how to login as another user.

### Project reflection

This project took me approximately 1h30 hrs  including demo time. The most challenging part was understanding the IAM policy since it was written with JSON and it contained multiple statements. It was most rewarding to see permission denied when our intern tried to delete our production instance. Our IAM access management setup is working.

---

## Tags

Tags are organizational tools that lets us label our resources. They are helpful for grouping resources, cost allocation and applying policies for all resources with the same tag.

The tag I’ve used on my EC2 instances is called Enviroment. The value I’ve assigned for my instances are Production and Development.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

IAM Policies are rules that determine who can do what in our AWS account. 

### The policy I set up

For this project, We've set up a policy using JSON. We are using policies today to control who has access to the production instances.

I’ve created a policy that allows the policy holder (i.e the intern) to have permission to do anything they want to any instances tagged with "development". They can also see information for any instance, but they are denied access to deleting or creating tags for any instance.

### When creating a JSON policy, you have to define its Effect, Action and Resource.

The Effect, Action, and Resource attributes of a JSON policy means whether or not the policy is denying/allowing action (i.e Effect), what the policy holder can/cannot is the (i.e Action) and the specific AWS resources that the policy relates to (i.e Resource).

---

## My JSON Policy

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_1c864649)

---

## Account Alias

An account alias is like a nickname for my AWS account instead of a long account ID - I can now reference my account alias instead.

Creating an account alias took me 30 seconds. Now, my new AWS console sign-in URL is the alias instead of my account ID.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### Users

IAM users are people who are entities that have access or can login into our SWS account.

### User Groups

IAM user groups are like folders that collect IAM users so that you can apply permission settings at the group level.

I attached the policy I created to this user group, which means any user created inside this group will automatically get the permissions attached to our NextWorkDevEnvironmentPolicy IAM policy.

---

## Logging in as an IAM User

The first way is to email sign-in instructions to the user. The second way is to download a .csv file with the sign in details inside.

Once I logged in as my IAM user, I noticed that our user is already denied access to panels on the main AWS console dashboard. This was because we only set up permissions to our development EC2 instance so our intern would not have access to even see anything else.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

I tested my JSON IAM policy by attempting to both the development and the production instances.

### Stopping the production instance

When I tried to stop the production instance we were met with an error. This was because our production instance is tagged with the production label which is outside of the scope of our permission policy - interns are only allowed to do things in the development instance.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_0e7a9d6a)

---

## Testing IAM Policies

### Stopping the development instance

Next, when I tried to stop the development instance, we succesfully saw the instance state to stopping then it stopped. This was because our permission policy allows the intern i.e users in the nextwork-dev-group to stop instances.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_1811801c)

---

## The IAM Policy Simulator

The IAM Policy Simulator is a tool that lets us simulate actions and test permission settings by defining a specific user/group/role and the action we want to test for. It's useful for saving time when testing permission settings. No more logging in to another user or actually stopping resources.

### How I used the simulator

I set up a simulation for whether our dev user group has permission to StopInstance or DeleteTags. The results were denied for both actions so I had to adjust the scope of EC2 instances to ones that are tagged with development and once we applied that tag, permission was allowed.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-security-iam_069d8a621)

---

---
