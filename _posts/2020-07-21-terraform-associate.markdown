---
layout: post
title:  "HashiCorp Certified Terraform Associate"
date:   2020-07-21 00:00:00 +0000
categories: terraform
---

There it is, **I am now a Certified Terraform Associate**. I decided to kick off this brand new blog with an opinionated review
of this certification and the required preparation. 

*Disclaimer: I am a huge HashiCorp fan!*

### Preparation

It was a while since I took any certification exam and was looking for something soft to get back in the game. I have about two years of experience with Terraform, so I felt that this certification would be a quick win. So I based my preparation from the official 
[Exam Review](https://learn.hashicorp.com/terraform/certification/terraform-associate-review) from HashiCorp. 

I probably spent around 20 hours preparing for the exam. I went through all the documentation from the exam review, topic by topic, 
skipping stuff that was part of my day-to-day. The preparation focus was a lot on the workflow, the commands, 
the usual meta-arguments (arguments like count), and base concepts.

To complete this, I bought the **HashiCorp Certified: Terraform Associate Practice Exam 2020** 
on [Udemy](https://www.udemy.com/course/terraform-associate-practice-exam) from Bryan Krausen. It was definitely aligned with
the kind of questions that were asked during the exam. I read that the actual questions were about 15% harder on some reviews, 
but I didn't felt this. 


### On exam day

This exam is scheduled through an online proctoring service called Examity. The scheduling process was easy. Connecting with
the proctor was also quite simple. You have an hour to answer about 60 questions (multiple choices, true/false). 
You can skip questions and come back later. You can mark a question for review. 

It took me about 20 minutes to make a first quick pass at all the questions. I marked a few ones for review. 
Few seconds after answering the last one, the Zoom meeting (that Examity use to monitor you during the exam)
disconnected. When this happens, the exam is paused, but the timer does not stop. 
I started working with Examity support using the chat function. Long story short, it took 45 minutes to get back on the Zoom meeting. 

The moment I got back on track, the exam automatically ended
(timer went all the way down to 0 and my proctor didn't pause it even though the support guy I was in contact with assured me they would).
Fortunately for me, I still passed with flying colors and got my badge. 
In that situation, I decided to not make a fuss about the lost time and went my merry way. 
If someone from HashiCorp ever read this... Examity... not a big fan!!

### Things I learned

Even though a lot of the content of the exam was knowledge I already had, I've learned a few interesting things that I wanted to mention

- You can speed-up significantly a `plan` or `apply` operation by using the `-refresh=false` flag to use the current state as-is. 
*While this could cause you to rely on a state that drifted from the real resources configuration, 
it has the benefit of accelerating the feedback loop a lot when implementing/testing a new part of your configuration.*

- To save the execution plan of a destroy operation, you need to use `terraform plan -destroy -out plan.out` not the `terraform destroy` command

- One should use the provisioner feature as a last resort for a lot of very logical reasons. 
The one I retain was that it makes Terraform a lot less portable as it creates external dependencies 
(like the availability of some local binaries or a requirement for direct connectivity).

- It is recommended to use a minimum version `>=` provider constraint for shared child modules. For root modules, the recommendation is to set both the lower and higher bounds `~>`
).

- You can locally cache provider binaries to speed up the `init` workflow and save on space (versus downloading them each time for each configuration)

- HashiCorp Vault looks like a pretty awesome secret management platform. I will definitely need to set up some lab in the short term to experiment.


### Conclusion

To sum up, I'd say it was a nice experience overall. The exam will most definitely not be a challenge if you have any real Terraform experience under your belt.
The exam cost is only 75$USD so it is an easy target on all fronts. Probably more at the "foundational" level of certification rather than at the "associate" one (in my opinion).
As the head of a Cloud Ops team, I would value this certification on an applicant's resume.

### Helpful reference

[HashiCorp Infrastructure Automation Certification](https://www.hashicorp.com/certification/terraform-associate/)

[Exam Review - Terraform Associate Certification](https://learn.hashicorp.com/terraform/certification/terraform-associate-review)

[A Guide to HashiCorp Certified Terraform Associate](https://medium.com/@sanoojm/a-giude-to-hashicorp-certified-terraform-associate-cd9b21699139)

[HashiCorp Certified: Terraform Associate Practice Exam 2020](https://www.udemy.com/course/terraform-associate-practice-exam)

<br/><br/>
<br/><br/>
<p align="center">
    <img src="{{site.baseurl}}/assets/img/terraform-associate-logo.png" width="200"/>
</p>