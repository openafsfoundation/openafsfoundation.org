---
title: Use Cases
nav: [tech,what]
---

## Use Cases ##

### Stanford Linear Accelerator Center ###

AFS supports all of the following projects in that most of the tools (compilers, CVS code trees, etc.) are in AFS as well as some of the data input and output for their simulations (some Monte Carlo type simulations but mostly data for GEANT simulations).

Here are three press releases about three very different branches of science going on at SLAC.

The first is about our biggest experiment, BaBar. They proved a certain kind of CP ("charge-parity") violation that explains in part the asymmetry between matter and antimatter. This explains (in part) why after the Big Bang more matter than antimatter was left over and the universe could form. BaBar has taken around 2 PetaByte of data sitting on tape but all their development tools and software code sit in AFS.   BaBar uses AFS for worldwide collaboration, and distribution of their code repositories.

    September 28, 2006 - New Form of CP Violation Discovered
    http://home.slac.stanford.edu/pressreleases/2006/20060928.htm

The second one is astrophysics research done at KIPAC (Kavli Institute for Particle Astrophysics and Cosmology). They did mass analysis of pictures from the Chandra X-ray Observatory and for the first time directly observed the Dark Matter. The data itself is again not in AFS but most of the development tools and software code is in AFS.

    August 21, 2006 - Dark Matter Observed
    http://home.slac.stanford.edu/pressreleases/2006/20060821.htm

The next two are about our Synchrotron Radiation Lab (SSRL). They highlight the application of SLAC's physics technology for completely different branches of science.

    August 2, 2006 - Modern Technology Reveals Ancient Science
    http://home.slac.stanford.edu/pressreleases/2006/20060802.htm

    Archimedes Manuscript Yields Secrets Under X-Ray Gaze
    http://home.slac.stanford.edu/pressreleases/2005/20050518.htm

SLAC is currently expanding the computer center's relationship with SSRL to provide AFS space for their tools like Gaussian (sequential and parallel). They have also started to use our standard software development tools (compilers, etc.) in AFS space.

Lastly, a very widely used toolkit, GEANT4 (http://geant4.web.cern.ch/geant4/), for the simulation of the passage of particles through matter is being co-developed at SLAC. Everything they do is in AFS. Among many, many other things, this toolkit is used for medical simulations of radiation treatments of tumors in the human body.

A summary of research performed at SLAC in 2006: http://today.slac.stanford.edu/feature/holiday-message06.asp

Since 1998, SLAC has stored all user home directories in AFS.  AFS is available to the several thousand machines in its batch farm and is used primarily for the delivery of binaries for batch jobs.

    How much data (in TB)?                 5.5TB
    How many users?                          3247
    How many volumes?                      18621
    How many file servers?                  15 fileservers
    How much storage per file server?   34GB to 1.6TB

### ParallellDatorCentrum, Center for Parallel Computers at KTH ###

One of the computing centers in Sweden for research. Situated at KTH, Royal Institute of Technology, Stockholm.  Written by Harald Barth.

#### Historical reasons ####

In the infancy of network file systems different parts of the decentralized computing service groups at KTH were looking for a platform independent file system. The choice fell on AFS from back then Transarc, a CMU spin-off. Now, 15 years later, I can still read the files I saved into AFS as a student from a completely different hardware and OS. Compare that to the problems some researchers have reading data from "the previous computer system" I only have to bow my head for the folks who made the decision back then.

Once you have all your data available all the time on all systems it is very convenient and all kinds of automated maintenance methods make use of the fact. To abandon AFS would make it necessary to rewrite all this - accumulated since approximately 1992.

#### Reasons important back then but not as important any more ####

As network speed has increased a factor of 100, hard disk speeds have only a factor of 10. So local cache on the workstations/computing nodes, once a crucial detail of AFS, is not the overall important reason to deploy AFS any more.

#### Reasons still important ####

Design of location independence. Users access their files though globally unique path names which do not change. Period. The file system handles all mapping behind the scenes where to find the data. This is a central and not optional design point of AFS. This idea has been reinvented several times (URLs, for example in grid software), but I dare to say that no other system has so completely hidden the location details from the user as AFS. As it is hidden, the user or the middleware implementer or whoever is not tempted to use the information (my data is on bighost-5.edu) in a way which might break the system in the future (his data has been moved to bighost-6.edu).

The volume abstraction. Users files and directories are organized as volumes which are mounted as a kind of virtual disks into the global file tree. This abstraction allows it to move data between different servers online. No more interrupts of long running programs to upgrade a software, server or a storage system.
        
Source availability. Since the beginning KTH has had a source license (later open source) of AFS. Even if it not used every day, the knowledge that you have the means to recover your data even should your file system software provider go out of business is a soothing experience.

System independence. Both server and client OS and versions can be exchanged freely. For example no problem to write data on MacOSX, store it on a mix of Solaris and Linux servers and read it back on Windows.

#### Challenges for the future ####

Encryption: AFS has means for data check summing and encryption. However the encryption standards of the 90s are not adequate any more. Work is in progress to support up to date encryption but could be sped up by adding developer time.

Network performance: The AFS protocol does not limit the implementation of additional network protocols and better bandwidth utilization in times where the speed of the network equals or excels that of the client HD. Developer time has to be spent to implement the mechanisms to do this in the framework of AFS.

#### AFS usage at PDC in numbers (2007-01-01)#### 

Number of Clients: Unknown. PDC manages 5 clusters with a total of more than 1200 computing nodes. When the clusters are new, they use to appear around rank 70 of the top 500 list. All production systems use AFS. There may be a single digit number of computers which have no access to the AFS space. Add to that the number of researchers who access their data from their own workstations from all over the Internet.

    Number of simultaneous users: 100-200.
    Number of users with $HOME in pdc.kth.se AFS space: Approx 3000.
    Amount of data in AFS: Approx 5TB.
    Number of volumes: Approx 6000.
    Number of files: Approx 65 000 000.
    Number of file servers: 11
    Approx storage per server: 1TB


### Pictage Inc.###

    http://www.pictage.com/

Pictage's business is worldwide.  They provide services to wedding photographers who upload the photos they have taken. Pictage then makes the photos available to the wedding party for photo selection and printing.  Photos selected for printing are retouched by hand using Adobe Photoshop.

Pictage uses OpenAFS to store all of the original photos, the processed photos, and the web content.

Work flow is managed by the use of mount points and symlinks which are placed within directories assigned to various photographers and their associated events. 

Pictage storage has exceeded 200TB of data and more then 40 million files.  They frequently push the limits of the AFS directory structures running into the directory entry limitations. 

Directory search performance is one of their bottlenecks.  Unlike more modern file systems, AFS does not use a B+ tree representation and directory searches within the case-insensitive Microsoft Windows client are linear in nature.  This wastes significant CPU utilization and clock time.  Pictage had measured the performance loss on a duo-core Xeon processor at between 3 and 5 seconds to open a file in Adobe Photoshop when the directory contains 15,000 entries, because Adobe Photoshop will request information forthe last 30 files it has seen, thus requiring heavy usage of AFS directories.   OpenAFS for Windows 1.5.13 added an optimization for cached files with registered callbacks that avoids the performance problem for files that are known to exist.  With this optimization in place, Pictage experienced file open times similar to those experienced when opening files on the local filesystem.  For files that do not exist such as Java class files, the optimization does not apply, and the linear search must still be used.
    Number of simultaneous users: 150 AFS client users; 1000 web server users
    Amount of data in AFS: Approx 215TB
    Amount of AFS storage: 265TB with planned growth to 425TB in twelve months
    Number of volumes: Approx 800,000.
    Number of files: Approx 200 000 000.
    Number of file servers: 70 with 10 more planned
    Approx storage per server: depending on age of server 1.2TB to 25TB
(statistics as of 22 May 2007)


### NCSA at UIUC###

HDF is a project that helps support the research projects that NCSA provides computing services for.

This page is prettier and has some more concise history:
    http://www.ncsa.uiuc.edu/News/Access/Archive/backissues/96.1/hdf-tng.html

They've recently split off from NCSA to form The HDF Group:
    http://www.hdfgroup.org/
    http://www.hdfgroup.org/users5.html
    http://www.hdfgroup.org/HDF5/release/platforms5.html

Their source tree and everything is in the NCSA AFS cell and the build process is scripted for all the different architectures they support.  Their build systems range from clusters to servers to desktop systems and the binaries can be dropped right into AFS which users grab via ftp.  They need an authenticated file system that supports all of those platforms.

NCSA's Security team uses AFS for storing security incidents and collaborating with off-site users.

And some comments from Christopher Lindsey about future directions:

  "I can tell you about possible future direction.

  "We've all noticed that the stand-alone University model doesn't work.  Just like businesses that merge, Universities are finding that they need
    to collaborate with other research institutions to make their proposals competitive.  You throw in concepts like grid computing (i.e. TeraGrid)
    and you suddenly have a diverse, disparate set of sites that need to collaborate.

  "This is where AFS becomes a player.

  "I believe that we currently use it as a giant swap file space for different projects -- one supercomputer site needs access to security
    net flows, so we put them out there, set the acls, and voila.

  "Future projects on supercomputers will leverage AFS as well.  I don't know how much detail I can go into, but there is a proposal that will
    be submitted on Jan 22 that will revolutionize how HPC resources within the TeraGrid are used.  The ubiquity and security of AFS make it the
    perfect foundation for this project.

  "As far as timings, we might be able to do some dprof timings between here and Argonne Labs over iwire (http://www.iwire.org/).  Ironically, the bottleneck there will be the GigE NIC on the AFS servers."


### United States Geological Survey###

####Background####

The use of AFS at the United States Geological Survey, USGS, started in response to a requirement to provide natural hazard information on the Web so that it could continue being delivered to the public even in the event of large-scale regional disasters.  The driver for this activity was the inability of US Geological Survey to provide water level measurements during hurricane  Floyd in 1999 just when that information was needed most by emergency managers, because our database servers and Web servers were rendered useless by power and networking failures in affected states.

This regionally distributed, "no single point of failure" delivery Web service relies in part on AFS to provide regionally replicated file content at "modules" housing AFS file servers and Web servers in Menlo Park, California, Sioux Falls, South Dakota, and Reston, Virginia.
    
####Why are we using AFS####

AFS was chosen as it was the only multi-platform software available to provide geographically distributed content replication, access control, and user transparency as required by our project.

####How we are using AFS####

Three Web servers at each module have an identical view of read-only copies of data provided by AFS. Bringing on additional Web serving capacity is as easy as adding another Web server which is also an AFS client.  A commercial DNS service with wellness checking, Akamai, resolves hostnames to these geographically distributed Web servers, which are checked every minute for availability.  Failure to contact Web service on any one of these systems results in the corresponding IP address being taken out of DNS resolution.

This National Web server system known as, NatWeb, delivers Web content for 150 unique USGS websites. In 2006  NatWeb delivered an average of 1.2 million web pages and 191 gigabytes of data per day, for an annual total of 453 million pages and 68 terabytes.  It has experienced a roughly 50% increase in utilization annually for the last three years.  We serve data as diverse as
        Toxic Substances Hydrology http://toxics.usgs.gov/,
        Northern Prairie Wildlife http://www.npwrc.usgs.gov/,
        The Cascades Volcano Observatory http://vulcan.wr.usgs.gov/,
        National flood and drought  conditions http://water.usgs.gov/waterwatch/ and
        3D  images of national parks http://3dparks.wr.usgs.gov/.

Our use of AFS is tied nearly exclusively to Web service.  All content is replicated to all regions.  The R/W master for content is located in the same region as content maintainers, so R/W and replicated R/O information is distributed evenly across regions. Any one region can drop from the network, and the associated Web information will continue to be served to the public, although updates cannot be accomplished in this condition without administrator intervention.

####AFS Site Size####

We are a small AFS site by most measures. AFS usage specifics (with some rounding):
        500 AFS users
        1300 volumes
        0.64 terabytes of data

Our architecture uses custom programming to detect changes to AFS content. Volumes containing  updated content are automatically released (replicated to remote locations) every 15 minutes. The file servers collectively execute over 2000 "vos release"s per day.

####Architecture####

Our server implementation is entirely Sun/Solaris 10 based.  At each of our three module locations:
        an AFS database server -- Sun 250
        3 AFS file servers, and 1 warm spare -- Sun V240
        all 4 file servers are directly attached to a Sun 3510FC Fibre Channel disk array (RAID 5 + 1)
        3 Web servers -- Sun V210

There are three hostname/IP address pairings by which all AFS file services are known, as well a separate hostname and IP address which is always associated with the same computer.  By shutting down AFS services, and shuttling the appropriate IP address from one system to another, we can effectively fail over AFS file service from one system to another.

Our AFS clients fall into two major categories, the Web servers which serve content to the public, and the content maintainers who have AFS installed on their desktops.

Our content maintainers are overwhelmingly using Windows XP, with perhaps 5% using Mac OS X and still smaller numbers using Linux and Solaris.

Our entire staff consists of 3 full-time employees, 1 part-time employee, and one manager. These individuals manage the budget, hardware, operating system maintenance, security, software updates, custom programming and user support for both the AFS and Web components of the service.
