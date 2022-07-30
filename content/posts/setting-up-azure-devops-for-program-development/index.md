---
title: Setting Up Azure DevOps for Program Development
date: "2020-08-30T17:43:37.121Z"
template: "post"
draft: false
category: "Azure DevOps"
tags:
  - "Agile"
  - "Azure DevOps"
description: "Using Delivery Plans in Azure DevOps allows you to manage program or product development while giving flexability to teams to work toward product/program goals."
socialImage: "/media/default-social-image.jpg"
---


# Introduction

Azure DevOps has some great features that can help you manage program or product development across teams. [Delivery Plans](https://marketplace.visualstudio.com/items?itemName=ms.vss-plans) is a [Visual Studio Marketplace](https://marketplace.visualstudio.com/) extension that helps teams align work by presenting a summary of the work being completed against an iteration based calendar.

## Getting Started
To get started with this feature, make sure you install the Delivery Plans extension. Your account or groups will need the proper [permissions](https://docs.microsoft.com/en-us/azure/devops/marketplace/how-to/grant-permissions?view=azure-devops). You'll see a new area under **Boards** called **Plans**.

If you need to setup a demo project with example stories, visit the [Azure DevOps Demo Generator](https://azuredevopsdemogenerator.azurewebsites.net/). You'll choose the template under **Microsoft Learn** and **Manage Agile software delivery plans across teams**.

### New Delivery Plan
You can create a new *Delivery Plan* from multiple projects and teams within your organization. The backlog view can be set to whatever *navigation levels* (ie Epics, Features, Stories) are accepted in your board settings.

1. Go to **Plans**.
2. Select **New Plan**.

![New Delivery Plan](/media/azure-devops-new-delivery-plan.png)

### Tracking Milestones
You can add markers to your project to signify milestones within your roadmap or program. These can be helpful to track to important dates or goal milestones (such as Black Friday hardening)

![Milestone Markers](/media/azure-devops-milestone-markers.png)

### Planning Your Backlog
If you installed the demo, you're in luck because you get a nice view of work items already setup in planned sprints. Within this view you can drag and drop stories from iterations for the same team. If you are starting with an existing project, or have yet to create elements of your team backlog you'll have a bit more work ahead of you.

> **Caution:** Be careful as you can also adjust backlog items in the current iteration without warning.

This view is extremely beneficial because it shows multiple team backlogs against iterations with a calendar view. Most stakeholders could care less about what sprint you're in, as long as you're trending toward milestones. This view also helps your team leads plan their team work against potential dependencies from other teams.

If you'd like to truly track against dependencies, check out the [Dependency Tracker](https://marketplace.visualstudio.com/items?itemName=ms-eswm.dependencytracker&ssr=false#overview) extension from Microsoft. More information on how it can be used can be found [here](https://docs.microsoft.com/en-us/azure/devops/boards/extensions/dependency-tracker?view=azure-devops).

![Delivery Plan Overview](/media/azure-devops-delivery-plan-overview.png)

> **Kanban Teams:** Since Kanban teams are not timeboxed, you may setup your iteration from an arbitrary start date until a far into the future. This causes a stacked view on the delivery plan and, depending on the backlog and WIP, may get nasty to navigate. Having said this, I wouldn't recommend tracking Kanban teams on a delivery plan as work is based on priority and managed with WIP limits. If you can manage the backlog and WIP to a relatively small number of items, there is good visibility into what the team is doing, however. This may be beneficial if you have a support team working with a delivery team to get visibility on dependencies.

Azure DevOps also has built in Planning that can be toggled in the backlog view. I bring this up because you may ask why you need to install an extension to get functionality that is already built into AzDO.

![Toggle Planning](/media/azure-devops-toggle-planning.png)

The main problem with this view is that you can only plan for a single team and it's difficult to see how a single team's work fits with multiple teams in a program or product. Plans can accomodate for multiple iteration levels and  dates - which is helpful when you have teams that may not align sprints.

### Working with Frameworks

The big question comes up, how do I work with my scaled framework?

Whether you're doing [Scrum of Scrums](https://scrumatscale.scruminc.com/scrum-at-scale-guide-online/), [SAFe](https://www.scaledagileframework.com/), [LeSS](https://less.works/), etc you're most likely going to need to manage multiple team backlogs. Whether you have a program backlog, EAT (Executive Team Action) backlog, etc that funnels into smaller team or feature backlogs you'll want visibility across related areas in your organization.

Azure DevOps is flexible enough to work in whatever framework you're using and this tool helps gives exeutive stakeholders and team members a closer glimpse into the goals and milestones of the organization.