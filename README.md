# PI Challenge

This is a challenge to push you to grow in the areas of infrastructure and automation.  This will take a long time to complete, and you will hit brick walls that will need to be scaled to move past.  I do expect everyone to take this challenge on, as you will learn something from it, even if you've done an exercise like this before.  The purpose of this is to grow, not drag you down, so don't let this get in the way of your normal work.  There is not timeline or due date,  you will have to take the initiative to be a self-starter.  You will not be graded or judged on this, it is literally to push yourself.

This challenge comes from when I started with a company.  I quickly recognized my need to ramp up with a mentality around automation, and created a similar challenge for myself.

This will be a fun, challenging experience, and will take time.  Don't get frustrated when you hit walls, push through them and be successful!

## The Challenge

Using a personal lab, hosting provider, or your workstation (if you're brave), create a blog that you will use to document your progress through this challenge.  This blog will need to have several components:

### Design Phase

1. A minimum of two load balancer nodes with some sort of fail-over capability to provide resiliency
2. A minimum of three web servers behind those load balancers to provide resiliency
3. A minimum of two database nodes for data protection
    1. You need to have db backups as well, that way you can restore the content when you tear this down and test your automation
4. Bonus points if your build in-memory caching into the solution

### Automation

1. Creation of nodes should be automated, there are a ton of tools to do this, research research research...
    1. Bonus points if you build automation to fully configure and deploy your automation server (hopefully Chef) as part of this, including uploading your roles, environments, and cookbooks
2. Your database should include automation to load your database content
3. Primary/Secondary DB relationships should be automatically configured
4. Web servers should search and find the database nodes to use and configure
5. Load balancer nodes should automatically find web servers and configure itself to use them
    1. even if you build a new web server, it should be automated well enough to pick up on that and start using it
    2. health checking should also be in place, so that the load balancer doesn't just start using a new server that hasn't been deployed to.

### Content Deployment

Your web site will have code that will change. You can choose to deploy this with your automation tool, or out of band with another tool.  I have long been of the opinion that chef is a configuration management tool, not a deployment tool; however, I want you to use this as an opportunity to form your own opinion.


1. If you use an out of band tool, it needs to integrate with your automation platform to dynamically generate nodes that need deployed to.

### Finalizing

1. When you are done, tear the entire thing down and run your automation to find lose ends and things you didn't think about
2. Make sure your code is stored in a repo
3. Schedule a demo!

I can't wait to see some demo's — even if it's in an incomplete state.  Getting ongoing feedback from your peers will help with your success!

