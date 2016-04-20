# doc-susemanager-new

#The SUSE Manager Documentation Update Repository#
![](http://i560.photobucket.com/albums/ss45/joecayouette/docuimage_2.png)
**This readme is currently under development**

This is the source for the official SUSE Manager documentation update.
This update aims to condense the current six SUSE Manager official documentation books into four brand new manuals. This update will include up-to-date & detailed information covering many subjects generated by feedback from customers, engineers, and sales. A short list of subjects being looked at & in improvment planning include:

* Channel Management
* Channel Assignment
* What is Channel Cloning 
* Cloning Tools
* Custom and Third Party Software
* Patching Systems
* Organization and Group Management
* Activation Key Management
* Bootstrap and Contact Methods: ssh push, pull, osad, saltstack
* Web User Interface
* Command Line Tools
* SUSE Manager Server Setup
* SUSE Manager Proxy
* Autoinstallation
* Best Practice Concepts
* Troubleshooting
* Subscription Counting
* Error feedback & logging
* Salt
* Contact Methods
* API Use
* rhn.conf parameters




*As this is a broad work, many topics to be updated will not be included in this list and topics are subject to change. We will attempt to keep this list up-to-date as documentation develops.*
 
##Current work list:##
New work items will be added here. The status of these items will be marked with:

* IN_PROGRESS
* DONE

##The Working List:##

- [x] ~~Git repo setup Status: DONE JUNE 2015~~
- [x] ~~New table of contents for books including customer, engineering & sales feedback Status: DONE JUNE 2015~~
- [x] ~~Channel Management research Status: DONE JULY 2015~~
- [x] ~~SUSE Manager and System z Guide in Advanced Topics Status: DONE JULY 2015~~
- [x] ~~Began periodic work with help from Kwalter on an internal feedback tool for connecting the                                     Q/A/Engineer/Developer/Documentation smokestack. AUG 2015~~
- [x] ~~Writethedocs Conference Prague Status: DONE AUG 31-SEPT 1 2015~~
- [x] ~~SUSE Manager 3 Quickstart Guide Installation Status: DONE SEPT 2015~~
- [x] ~~SUSE Manager 3 Quickstart Guide Setup Status: DONE OCT 2015~~
- [x] ~~SUSE Manager 3 Quickstart Guide Status: DONE OCT 2015~~
- [x] ~~Quickstart Using Salt (Technical Preview) Status: DONE NOV 2015~~
- [x] ~~Updated all documentation from DocBook version 4.5 to 5.1 Status: DONE NOV 2015~~
- [x] ~~Internal Feedback tool code-name :DocReview:  Status: DONE NOV 2015~~
- [x] ~~Current work on docs released in SUSE Manager Technical Preview Status: DONE NOV 2015~~
- [x] ~~Best Practice Introduction Status: DONE NOV 2015~~
- [x] ~~Updated Book chapter/section ID's to match SUSE Manager WebUI KE/MC/Coyote Status: DONE JAN 2016~~
- [x] ~~Contact Methods rhnsd, ssh push, ssh push tunnel, osad (BP guide) DONE FEB 2016
      (Salt to be added IN_DEV)~~
- [x] ~~Managing Entitlements SCC and SMT (BP Guide) Status: DONE FEB 2016~~
- [x] ~~Reference Book update Status: DONE FEB 2016~~
- [x] ~~Advanced Patch Lifecycle Management (BP Guide) Status: DONE FEB 2016~~
- [x] ~~Activation Key Use and Guidelines Status: DONE MARCH 2016~~
- [x] ~~Subscription Matching Training and Writeup (BP) Status: DONE MARCH 2016~~
- [x] ~~Document New Salt Features (BP/REF) Status: DONE APRIL 2016~~
- [x] ~~SUSE Manger Migration from 2.1 - 3 Status: DONE April 2016~~
- [ ] System Details Salt State Components (Packages, Custom, Highstate) Status: IN_PROGRESS APRIL 2016

##Planning:##

**Four book are currently PLANNED:**
* Getting Started
* Best Practices
* Reference
* Advanced Topics




##Contributing##

If you would like to contribute, please fork this repository and send pull requests.

Contributors with direct access to the repository are encouraged to use the git-flow-avh workflow (package git-flow-avh).
Note:
	
Please do not make any commits to the master branch. master is reserved for releases only. 


##Updating the SUMA 3 Documentation Package (susemanager-docs_en)##

```
OBS_USER=keichwa

daps -d DC-create-all package-src --set-date=$(date --iso) \
     --def-file DEF-susemanager-docs

# save old checkout
old home:$OBS_USER:branches:Devel:Galaxy:Manager:Head/susemanager-docs_en

osc -A https://api.suse.de bco Devel:Galaxy:Manager:Head susemanager-docs_en
cd home:$OBS_USER:branches:Devel:Galaxy:Manager:Head/susemanager-docs_en
cp ../../build/create-all/package/create-all_en_src_set.tar.bz2 .
osc vc -m "Update text and image files."
osc ci -m "update"

# check results; e.g. with:
osc pr

osc sr -m 'update'
Perform these steps on both head and 3.0

```

##Preparing and Publishing Online Documentation (suse.com/documentation)##

ATM (2016-04-20), you must you a recent daps checkout from
git@github.com:openSUSE/daps.git.

Switch to the documentation checkout and call:

```
.../daps/bin/daps --dapsroot .../daps -d DC-create-all online-docs \
  --dbtonovdoc
```

Copy the results to the results to your ~/Exports directory.

Create a bug (Classification: Doc Tools, Product: Doc Production,
Component: SUSE Manager) and ask to update
suse.com/documentation/suse-manager-3 accordingly.  As an example, see
https://bugzilla.suse.com/show_bug.cgi?id=975925 .


##Updating SUSE Manager API Documentation and Posting Online##

SUSE Manager 3 (SLE 12 SP1 example):

```
# rename existing directory
old binaries

# checkout the official binary packages
iosc getbinaries SUSE:SLE-12-SP1:Update:Products spacewalk-java standard x86_64

# get the docbook file
unrpm binaries/spacewalk-java-apidoc-sources*
# ==>
# usr/share/doc/packages/spacewalk-java/xml/susemanager_api_doc.xml

# build the PDF with daps:
daps -m usr/share/doc/packages/spacewalk-java/xml/susemanager_api_doc.xml pdf
```

Then create a bug (Classification: Doc Tools, Product: Doc Production,
Component: SUSE Manager) and ask to update
suse.com/documentation/suse-manager-3 accordingly.  As an example, see
https://bugzilla.suse.com/show_bug.cgi?id=976225 .

##Publishing Release Notes on https://www.suse.com/releasenotes/##

If not already done, ask Rudi or Lars (Vogt) to mirror the release notes
from the release repo, and then add the new version to
https://www.suse.com/releasenotes/ .  After publishing the first update,
you probably ask Rudi or Lars again to the mirror script.
