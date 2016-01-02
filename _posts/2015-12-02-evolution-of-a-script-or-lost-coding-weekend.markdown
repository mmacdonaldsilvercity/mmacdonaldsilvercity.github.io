---
published: true
title: Evolution of a Script or: Lost Coding Weekend
layout: post
---
<!DOCTYPE html>
<html>
<head>

  <meta charset="UTF-8">
  <title>Evolution of a Script or: Lost Coding Weekend</title>
  <meta name="viewport" content="width=device-width">

  <!--[if lt IE 9]>
    <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
  <![endif]-->

  <link href="/assets/css/style.css" rel="stylesheet" />
  <link href="/assets/css/colors-dark.css" rel="stylesheet" />

</head>

<body>

<header id="header">
    <h1><a href="/"><i class="icon-sun"></i> </a></h1>
    <p>A long career, with a lot of different experiences in corporate Information Technology provides a backdrop for observing the IT-scape.</p>
  </header>
  <div id="page">
    <div id="sidebar">
      <nav>
        <ul>
          <li><a href="/">Home</a></li>
          <li><a href="/archives">Blog Index</a></li>
          <li><a href="/about">About</a></li>
          <li><a href="http://twitter.com/mmacdonaldscp">Twitter</a></li>
          <li><a href="/feed.xml">RSS Feed</a></li>
          <li><a href="mailto:contact@silvercityenterprises.com">Respond</a></li>
        </ul>
      </nav>
    </div>
    <div id="content">
      <article class="post">

	
		<h1><a href="http://mmacdonaldsilvercity.github.io/2015/12/02/evolution-of-a-script-or-lost-coding-weekend.html">Evolution of a Script: Or Lost Coding Weekend</a></h1>
<div class="post-content">

<p>Yeah, all programmers are lazy.  That's why they program computers to do their scut-work, right? </p> 

<p>And maybe they save themselves some time, mostly.  Then again, sometimes these general purpose computers call to us, saying "Lookit all the groovy things I can do!  Program me!"  And it is a false promise, because sometimes it's just plain easier and quicker NOT to apply a technical solution.</p>

<p>In other words:  How I Ate Up Every Spare Minute of My Thanksgiving Long Weekend...</p>

<p>It started out innocently enough.  Long about a year or so ago a very learned and wise Super Programmer sent me a quick email outlining how to configure SSH server logons so that no password is needed to be remembered.  For the first three or 8 times I wanted to implement an update to ~/.ssh/config, I searched around in a year's worth of email archives, and a thrown together binder of technical notes, a pile of gonna-writet-these-up post-its, until I located the instructions again. </p> 

<p>Hey, done this three times (or more); time to automate it!</p>

<p>Simple script.  What, 3 lines?  What did it look like again? ... Oh, 4 lines:</p>

<code>  

echo "Host $2" >> ~/.ssh/config   
echo "   Hostname $S1" >> ~/.ssh/config   
echo "   User $S3 " >> ~/.ssh/config   
ssh-copy-key   

</code>

<p>All well and good.  Except, gee, there is a pre-requisite -- the command ssh-keygen needs to be run one time, and when I've moved from one environment to another I've had to reenter that.  See above for the search algorithm, since my memory is like a sieve and I need to see the doc.</p>

<p>Heck, there must be a way to check for whether that's been run.  Sure enough, there are some files created in the ssh config directory.  Just gotta look for those there first, and run the command if they aren't.</p>

<p>Wait.  It's bad form to muck around with an administrator's configurations without warning.  I'll have to ask if it's ok to do that update.</p>

<p>At this point, my perspective went awry, and I got the wild idea that maybe, just maybe, there might be one or two linux users out there who haven't mastered this little trick, and actually might find a use for this script.  Hmmm... Well, if that is the case, I better check for those parms.</p>

<p>Did I ever know how to check for parms in bash scripts?  If I did, I forgot it or it got mixed up with other formats of the same thing in other languages.  ... Oh, getopts.  But it checks for switches, not positional parms.  No biggee.</p>

<p>Hold on -- There must be some technique for checking for positional parms also.  Of course there is! </p> 

<p>But wait, what if not all the parms are listed?  OK, gotta check to see if all three parms are there, or none.  But there are switches for the three inputs required; what if the operator enters only 2 of them?  Ok, more logic there.</p>

<p>Meanwhile, I've tested with my live ssh config file.  It now looks like garbage.  Another idea!  I've used the dry-run option on a bunch of commands, so that I could see what I'd break...</p>

<p>...and so on and so on.  The script is now 260 lines, including the -h text.  (See it on github at [https://github.com/mmacdonaldsilvercity/NewSSHLogon.git](https://github.com/mmacdonaldsilvercity/NewSSHLogon.git) And, just to prove how easily developers get carried away, I'm thinking that this could make a really nice template for the next time that I want to convert a 3 or 4 line command sequence into a lost weekend...</p>

</div>

	<p class="meta">Posted on <span class="postdate">Jan 02, 2016</span></p>

</article>

    </div>
  </div>
  <footer id="footer">
    <p class="copyright">Copyright &copy; 2016 . Powered by <a href="http://jekyllrb.com">Jekyll</a>, theme by <a href="http://www.webmaster-source.com">Matt Harzewski</a></p>
  </footer>
  <script src="//ajax.googleapis.com/ajax/libs/jquery/1.10.1/jquery.min.js"></script>
  <script src="/assets/js/jquery.mobilemenu.min.js"></script>
  <script>
    $(document).ready(function(){
      $('#sidebar nav ul').mobileMenu({'topOptionText': 'Menu', 'prependTo': '#sidebar nav'});
    });
  </script>



</body>
</html>