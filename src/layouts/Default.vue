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
            <g-link
              class="navbar-brand"
              to="/"
            >
              Blogio
            </g-link>
          </div>
          <div class="navbar-collapse collapse">
            <!-- Right nav -->
            <ul class="nav navbar-nav right">
              <li>
                <g-link to="/">
                  Home
                </g-link>
              </li>
              <li class="has-dropdown">
                <a href="#">Categories<i class="fa fa-angle-down" /></a>
                <ul class="dropdown-menu">
                  <li
                    v-for="{ node: category } in $static.context.edges"
                    :key="category.slug"
                  >
                    <g-link :to="`/blog/category/${category.slug}`">
                      {{ category.title }}
                    </g-link>
                  </li>
                </ul>
              </li>
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
              <g-link to="/">
                Home
              </g-link>
            </li>
          </ul>
        </div> <!-- End .footer-nav -->
        <div class="copyright">
          <span>Copyright 2015, All Rights Reserved Themography</span>
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
    context: allContentfulCategories {
      edges {
        node {
          title,
          slug
        }
      }
    }
  }
</static-query>

<script>
import Sidebar from '../components/Sidebar/Sidebar.vue'

export default {
  components: { Sidebar }
}
</script>
