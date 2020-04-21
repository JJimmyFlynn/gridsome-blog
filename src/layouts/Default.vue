<template>
  <div>
    <header
      id="header"
      class="header navbar-fixed-top"
    >
      <div class="container">
        <!-- Static navbar -->
        <div
          class="navbar"
          role="navigation"
        >
          <div class="navbar-header">
            <button
              type="button"
              class="navbar-toggle"
              data-toggle="collapse"
              data-target=".navbar-collapse"
            >
              <span class="sr-only">Toggle navigation</span>
              <span class="icon-bar" />
              <span class="icon-bar" />
              <span class="icon-bar" />
            </button>
            <a
              class="navbar-brand"
              href="#"
            >Blogio</a>
          </div>
          <div class="navbar-collapse collapse">
            <!-- Right nav -->
            <ul class="nav navbar-nav right">
              <li>
                <a href="#">Home<i class="fa fa-angle-down" /></a>
              </li>
              <li>
                <a href="#">Page<i class="fa fa-angle-down" /></a>
              </li>
              <li><a href="#">Archive</a></li>
              <li><a href="#">About Me</a></li>
              <li><a href="#">Contact Me</a></li>
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
    <slot name="upper" />

    <section id="content">
      <div class="container">
        <div class="row">
          <div class="col-md-8">
            <div class="primary">
              <slot />
            </div>
            <!--
                ===============
                  End .primary
                ===============
            -->
          </div> <!-- End .col-md-8 -->
          <div class="col-md-4">
            <Sidebar />
            <!--
               =================
                 End .sidebar
               =================
            -->
          </div> <!-- End .col-md-4 -->
        </div> <!-- End .row -->
      </div> <!-- End .container -->
    </section>

    <footer
      id="footer"
      class="footer"
    >
      <div class="container">
        <div class="footer-nav">
          <ul class="nav navbar-nav">
            <li class="active">
              <a href="#">Home</a>
            </li>
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

<script>
import Sidebar from '../components/Sidebar/Sidebar.vue'

export default {
  components: { Sidebar }
}
</script>
