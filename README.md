# VirtualMachine

### Description
I've done a couple projects now with the assumed knowledge of how to create and use virtual machines, so I thought it would be a good time to create a simple project that shows how we download and install virtual machines. This will be short, fun, and hopefully useful!

### Environments Used
- **Windows 10**
- **Oracle Virtual Box**
- **VMware Workstation**

### Downloading The Needed Files

In order to create and use virtual machines, we need a few things. Namely, the ISO of the OS we want to use, in this case, Windows 10, and the hypervisors that will let us use them, Oracle Box and VMware Workstation. Lets start with Windows 10. Use your search bar to search "Windows 10 download." In this photo, we will click on the top link. 

![Vulnerability Lab](https://imgur.com/4uRH9Vr.png)

Here, we will click on "Download Now" where it says "Create Windows 10 Installation Media."

![Vulnerability Lab](https://imgur.com/El04QJn.png)

We double click on our download when it's done and run it. We say yes, and then we select "Create installation media(USB drive, DVD, or ISO file) for another PC. Press yes, next, and then select ISO File. 

![Vulnerability Lab](https://imgur.com/Hsggxq1.png)
![Vulnerability Lab](https://imgur.com/a3J9n3T.png)
![Vulnerability Lab](https://imgur.com/4mmOeUZ.png)

Once it finishes downloading, we have a file called "Windows" in our download folder which we double click on, then doubleclick on setup. 

![Vulnerability Lab](https://imgur.com/mmqwUkQ.png)
![Vulnerability Lab](https://imgur.com/Aja34g3.png)

We select ok a few times, next, and accept the license aggreement. We have nothing to keep, so keep the option at nothing. 

![Vulnerability Lab](https://imgur.com/XevSvut.png)
![Vulnerability Lab](https://imgur.com/gqWQm6Y.png)

After it does its first scan, we can see that it really didn't show much, which is strange because this is a fresh Windows 10 install with no updates.

![Vulnerability Lab](https://imgur.com/iukVA0b.png)

To allow Nessus to get more in-depth scans, we need to configure a few things. First, we need to go to services and turn on the Remote Registry.

![Vulnerability Lab](https://imgur.com/Qw8PJcg.png)

Next, we need to make sure all network file and print sharing is turned on.

![Vulnerability Lab](https://imgur.com/iaQFPxW.png)

We then need to set "never Notify" on the User Account Control.

![Vulnerability Lab](https://imgur.com/3EJPMDT.png)

Finally, we need to create this registry in this location and set it to 1. You should never take these steps on a machine you are using; we are only doing it because this machine is not on a domain, so I have to make it accept the scanner.

![Vulnerability Lab](https://imgur.com/y3JamRH.png)

After making those changes, we do a restart and another scan. Now that the machine is letting the vulnerability scan go deeper, we find many more vulnerabilities and suggested remediations.

![Vulnerability Lab](https://imgur.com/L4eLCwl.png)

![Vulnerability Lab](https://imgur.com/4DbAYGD.png)

![Vulnerability Lab](https://imgur.com/wki4iJN.png)

Now, to give it more to look at, we will install a very old and insecure version of Firefox.

![Vulnerability Lab](https://imgur.com/eG2t8MG.png)

We run the scan again, and we have way more vulnerabilities than we did before.

![Vulnerability Lab](https://imgur.com/nCvklVo.png)

![Vulnerability Lab](https://imgur.com/zp2Mmfx.png)

![Vulnerability Lab](https://imgur.com/BIHP50M.png)

Now we remediate! In this scenario, we decide we don't want to allow Firefox, so we remove it entirely (risk avoidance). We then run the Windows Update utility a few times.

![Vulnerability Lab](https://imgur.com/htHxdFF.png)

![Vulnerability Lab](https://imgur.com/pkqyf82.png)

After removing Firefox and running Windows Update, we are already much better off than we were just a few minutes ago.

![Vulnerability Lab](https://imgur.com/fs9ZDFu.png)

![Vulnerability Lab](https://imgur.com/cQjqgSj.png)

![Vulnerability Lab](https://imgur.com/j8MGz4k.png)
