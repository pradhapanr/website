---
layout: page
title: Snowflake Work Term Report
permalink: /snowflake-report/
---

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/snowflake-office.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In my final co-op term in the summer of 2023, I joined Snowflake as a software engineering intern in San Mateo, Caifornia.
Over the course of 4 months, I was able to learn a lot about Go, Terraform and cloud engineering skills to scale a product
to thousands of large scale customers, processing terabytes of data every second.

### What is Snowflake?

Snowflake is a cloud computing based data cloud company, offering cloud based data storage and analytics. The main features
of Snowflake come from its separation of storage and compute, which allows you to scale each one individually to account for
your tailored needs, and keep costs at a minimum. Snowflake operates on all three major cloud platforms: AWS, Azure, and GCP.

<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/thierry.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/benoit.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Pictured above are the cofounders, Benoit Dageville and Thierry Cruanes. Snowflake began in 2012 in San Mateo after
Thierry and Benoit left Oracle as experts in data warehousing. Both were not satisfied with the use of Hadoop in industry,
and decided to make a better solution that was easier to adopt for teams with reduced complexity for managing large data.
Snowflake went on to have the biggest software IPO ever, raising nearly $3.4 billion.

### Goals

My first goal was to gain proficiency in the two new technologies I'd be learning at this internship: Go and Terraform. Go
was already on my list of languages to learn due to its constantly growing use in infratsructure, distributed computing,
and cloud computing which are my areas of interest. In my previous internship, I worked with CloudFormation which is an AWS
IaC solution, but Terraform is general purpose and can target all cloud providers which makes it a popular choice in
industry. Over the course of this internship, I worked closely with these technologies to make my internal cloud tool, which solely comprised of Go and Terraform. The measure of success I used was upon review of my PRs, see how many comments were left before the changes I made were successfully merged. As I created more PRs, I saw that the amount of feedback required before my code was merged reduced gradually, indicating my proficiency in the two languages increased.

My second goal was to improve my communication with stakeholders. At previous internships, I struggled to mention changes to
designs or deadlines with all stakeholders that would ideally be informed ASAP, which lead to confusion about project status.
Communication is a crucial skill that I wanted to see improvement in, and I had a good opportunity since I was reporting to a
few people about my project. To start, I created a list of project milestones with appropriate deadlines, and reviewed these
at the beginning of each week to check if I'm on track to meet these goals. I also designated time during 1-on-1s with my
manager and my mentor to discuss these milestones, just to make sure they were in the loop on any changes to deadlines or
updates to the project as a whole. At the beginning of the internship, I did not have a solid plan laid out for my design
which lead to some communication struggles at first, but once the milestones were laid out, I saw significant improvement
in communication to both my manager and mentor. By the end of my internship, my manager let me know that my communication
had improved significantly and we were able to avoid the same lapses in communication that occurred in the first month.

My final goal was to continue to improve my level of independence. I think this is a skill that I'm already quite proficient
in, but I recognize this is an ability that I will need as I progress in my career with more responsibilities placed on me.
It would look great if as a new grad engineer that I can produce at a capacity higher than the entry level bar out of the
gate, without requiring too much assistance. One thing I'm doing is restricting myself ot longer chunks of time
investigating issues before I seek help from someone else on the team (usually 2-3 hours max). This way, I can exhaustively
search through Confluence/Slack/Internal Docs/Google for solutions before I reach out to someone. Even if I am not able to
find an exact solution at this point, I would definitely be able to eliminate a lot of options, and usually be in the right
spot with some smaller clarifications needed to get there. During our midpoint and final review of my internship, both my
mentor and manager expressed my ability to operate independently exceeded their expectations, so I consider this goal a
great success.

### Job Description

During my time at Snowflake, I worked in the cloud engineering organization on the deployment automation team (nicknamed
Avalanche). We primarily maintained a tool that makes creating and maintaining deployments of Snowflake much simpler.
Prior to this tool existing, it would take almost 2 months to bring up a completely new production level deployment of
Snowflake, which is now reduced to the span of a day typically. When this idea was conceived, speed and stability was
a top priority. They decided to build with Go since it was built for concurrency, and was widely adopted by infrastructure
engineers. Because Snowflake is a multi cloud product, we used Terraform for cloud agnostic infrastructure solutions.

<div class="row justify-content-sm-center">
    <div class="col-sm-3 mt-3 mt-md-0">
        {% include figure.html path="assets/img/gopher.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/terraform.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


The tool I built for Avalanche helped propogate updates across our set of deployments in one click. Updating multiple
deployments can be a hassle, as you have to manually approve the changes to each deployment and review the changeset
as well to ensure nothing bad is happening. We saw an opportunity for automation by propagating the approval of a change
to other deployments if the initial state of the deployment was the same, and the changes being applied were the same as
well. However, when you compare any two terraform changesets (plans)from two separate deployments, even if the same
resources are being provisioned, there will always be unique values specific to that deployment. This means that two
changesets in their raw form will never be the same character by character. To avoid this, I created a diff framework that
allowed us to set custom equality functions to the comparison of two datatypes. This way, we can effectively ignore
properties that would always be unique in two deployments, or apply certain comparison rules to other properties that are
very close to being similar. This allows us to normalize our data such that we can get an equal comparison between two
changesets that are technically doing the same thing, but appear different due to deployment uniqueness.

### Conclusion

Overall, I was really happy to be with Snowflake this summer. It was nice to enter a new company after repeating my AWS
internship in the winter, and granted me a really diverse perspective into building new cloud infrastructure tools from
the ground up. I also got to work with some new languages and technologies that I had already been interested in, so working
with them in a production environment was really enjoyable. I also got the oppportuity to relocate to San Mateo, California,
where I met a bunch of new people that I will definitely be going back to see. There were also a lot of students from other
Canadian universities who I have already met up with since we have all gotten back. It really was an unforgettable
experience.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/yosemite.JPG" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Spent a weekend at Yosemite doing some gruesome hikes for amazing views.
</div>

### Acknowledgments

Shoutout to my mentor and manager who brought me up to speed with an incredibly complex internal tool, and provided me
the support necessary to succeed in the short time I was there. The other interns were also really great to hang out with,
and it was always nice to decompress after work with a nice session of pool or poker with them. I hope to see them all again
in the future!
