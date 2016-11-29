# Amazon work spaces

Presenter: Salman Paracha, Product Manager, AWS

Datetime: Tuesday, November 29th, 2016

## Goal before

* Learn ore use cases for work spaces
* Learn how to setup new work spaces
* Learn why I'd want work spaces over a VM
* Learn if it's possible to replace a traditional desktop with these work spaces

## Preview/Overview

* Talk about security
* What you'd use it for
* Talk about the failed promises of on-premises VDI
* Capabilities
* Overview
* Key benefits
* Stories of users

## What's the motivation to use

* Admins:
  * Securing resources
  * Lowering cost structure
  * Ease to administrate the machines
* Users:
  * Instant access
  * On any device


### On pre-VDI

* High expense
* Hard to scale
* Specialized resources -- better spent on company specific needs rather than using individual devices


### Desktop AWS -- features

* Pay as you go
* Desktop is secure because it's sent over AES encryption
* Encrypted at rest and in transit
* Should have fast internet on the machine
* Only pay for licenses that get used, don't worry about having a lot of them
* Monitors the desktop for you
* No data leaves your workspace because it's in the "cloud"

### Use cases

* Knowledge Workers - bring your own device
* Merges and acquisitions
* mobile Workers
* Temporary Workers
* Securing data
* Dev/Test
* Compliance requirements
* Call Centers
* Training and labs
* Developers -- I'll need to see this example, my mac is pretty good so far

### Benefits

* Much easier to do deployments of the "devices"
* Cloud watch monitoring for your devices
* Physical and virtual deployments are simplified
* Does well with existing stuff
  * Active Directory
  * Intranet
  * MFA
  * SCCM (I've no idea what this is...)
* Billing options:
  * Monthly
  * Hourly


### Added bits

* MFA
* Printers
* SSO
* Chromebook support
* High DPI screens
* Graphics work spaces
* Web based access to workspace
* Windows 10 will be available workspace soon! -- there is much excitement

## Live Demo

* Can launch a work space
* You select a directory (active directory?) -- no details given on how you make the directory to begin with
* Create a user or select users
* Next up you select bundles (basically the strength of the machine AND OS AND software)
* Running mode
  * Always on -- will never go down and is billed Monthly
  * AutoStop -- hourly billing, stopped with data saved to disk, slower start about 60 seconds, auto off will be based on time you choose
* Encryption -- you can encrypt the data if you want, you choose an AWS key that already exists or make a new one
* Tag -- makes it easy to see how a machine contributes within an organization, it's a tag...
* Launch the workspace last...... BOOM takes a minute or so and then it starts up
* Email sends to the user for logging in if there is no AD setup

### Directory follow up

* Access to Internet settings
* Security Groups settings, e.g. only allowed certain ports open
* Can setup web based access via Chrome or Firefox
* Maintenance mode so it'll update the machine for you 1 time a month

### Connecting

* Can see the info on the network if you look at the (i) button on the bottom right
* 200ms download speed required
* Consistent performance for the end user
* AWS backbone for internet speeds -- they are happy about 150Mbps download, fiber is more impressive

## User Stories

* Yamaha was able to get new software and use work spaces instead of buying new hardware

## Q/A

* Security software could mess up login
* The bundles come with some anti-virus installed
* They do not reveal the CPU architecture to customers (obviously)
* They provide consistent performance -- don't worry about low level details
* 45-60 seconds from a "hibernated" work space
* Turn of patches and AWS does not patch -- except zero day hits
* Goal to make HIPAA compliant in the future
* Two Nics attached to your device (one for your network and one for AWS network)
* Goal to have office 365 on the device as a bundle, not out yet
* Does not monitor the applications installed by users
* Not allowed to discuss road map....
* USB pass through is allowed for basically drives, not so much cameras
* Handles the orientation settings when you connect, so multiple monitors could be used
* Expiring users would need to happen via API settings
* Plan to support Windows 10 -- no Windows 8 will happen
* Connections are through the AWS gateway
* Multi region fail over is not yet there
