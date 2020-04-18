<template>
  <div>
    <header id="header" class="header navbar-fixed-top">
      <div class="container">
        <!-- Static navbar -->
        <div class="navbar" role="navigation">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
              <span class="sr-only">Toggle navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <a class="navbar-brand" href="index.html">Blogio</a>
          </div>
          <div class="navbar-collapse collapse">
            <!-- Right nav -->
            <ul class="nav navbar-nav right">
              <li><a href="index.html">Home<i class="fa fa-angle-down"></i></a>
                <ul class="dropdown-menu">
                  <li><a href="index-full-width.html">Full Width Blog</a></li>
                  <li><a href="#">Masonry Blog<i class="fa fa-angle-right"></i></a>
                    <ul class="dropdown-menu">
                      <li><a href="3column.html">3 Column Full</a></li>
                      <li><a href="2column-sidebar.html">2 Column with Sidebar</a></li>
                    </ul>
                  </li>
                  <li><a href="index2.html">Style 2</a></li>
                </ul>
              </li>
              <li><a href="#">Page<i class="fa fa-angle-down"></i></a>
                <ul class="dropdown-menu">
                  <li><a href="single.html">Single Page</a></li>
                  <li><a href="gallery.html">Gallery Post</a></li>
                  <li><a href="image-post.html">Image Post</a></li>
                  <li><a href="audio.html">Audio</a></li>
                  <li><a href="video.html">Video</a></li>
                  <li><a href="404.html">404 Page</a></li>
                </ul>
              </li>
              <li><a href="archive.html">Archive</a></li>
              <li><a href="about.html">About Me</a></li>
              <li><a href="contact.html">Contact Me</a></li>
            </ul>
          </div><!--/.nav-collapse -->
        </div>
      </div> <!-- End .container -->
    </header>
    <!--
        =====================
              End Header
        =====================
     -->

    <slot />

    <footer id="footer" class="footer">
      <div class="container">
        <div class="footer-nav">
          <ul class="nav navbar-nav">
            <li class="active"><a href="index.html">Home</a></li>
            <li><a href="#">Privacy & Policy</a></li>
            <li><a href="archive.html">Archive</a></li>
            <li><a href="about.html">About Me</a></li>
            <li><a href="contact.html">Contact Me</a></li>
          </ul>
        </div> <!-- End .footer-nav -->
        <div class="copyright">
          <span>Copyright 2015, All Rights Reserved <a href="#">Themography.</a></span>
        </div> <!-- End .copyright -->
      </div> <!-- End .container -->
    </footer>
    <!--
       =======================
         End Footer
       =======================
    -->
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>
