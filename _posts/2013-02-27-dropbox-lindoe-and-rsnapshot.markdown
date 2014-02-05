--- 
layout: post
status: publish
published: true
title: DropBox, Lindoe and rsnapshot
author: ldubber
author_login: ldubber
author_email: luke.dubber@gmail.com
author_url: http://www.lukedubber.com
wordpress_id: 6
wordpress_url: http://www.lukedubber.com/?p=6
date: 2013-02-27 08:56:22 -09:00
categories: 
- System Administration
tags: 
- Linode
- DropBox
- rsnapshot
- Linux
- Apache
- symlinks
comments: []

---
So I was trying to come up with a good way to backup my <a href="http://www.linode.com" target="_blank">Linode</a> box, now I have been thinking about this for a while, I put it on the back burner until quite recently when I finally got a <a href="http://db.tt/U3XsL636" target="_blank">DropBox </a>(seriously if you don't have one get one!) account. Now that I have one and have seen the potential I decide to see if I could use this to sync up backups to my desktop from the Linode server.

I used <a href="http://rsnapshot.org/" target="_blank">rsnapshot</a> to do the daily backups into my DropBox folder. I only backup the htdocs, <a href="http://apache.org" target="_blank">Apache </a>configs, and an export of my databases since that is all I need to be able to restore or move my sites over. Now the only issue I have had with DropBox and Linux has been the issue of <a href="http://en.wikipedia.org/wiki/Symbolic_link" target="_blank">symlinks</a>, it does not support them. So if you are backing up 100 megs of data the first day and then you backup again the next day and there are no changes. You still end up with another 100 megs. You can do the math its not ideal. But I figured since I don't have much and its better then nothing I am going to stick with it. Now if you know what you are doing with rsnapshot you can secure copy them over SSH to another box. I plan on doing that next so that files are backed up to my local <a href="http://en.wikipedia.org/wiki/Linux" target="_blank">Linux </a>box at home (even though just using Dropbox on that machine and a rsync would be enough).

Bellow are the steps to do what I have done. They are quick and a little light on details.
<ol>
	<li>Get a <a href="http://db.tt/U3XsL636" target="_blank">DropBox </a>account.</li>
	<li>Setup the <a href="https://www.dropbox.com/install?os=lnx" target="_blank">Linux client </a></li>
	<li>Install rsnapshot and set it up for the directories you want and point it to your Dropbox folder</li>
	<li>Done</li>
</ol>
Only side note is if you use this Dropbox for personal make sure you exclude it from your personal machine. That way you don't end up with a gigs of backups syncing all the time.
