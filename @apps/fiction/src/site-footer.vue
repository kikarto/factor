<template>
  <div class="content-footer">
    <div class="content-footer-pad">
      <div class="footer-col">
        <factor-link path="/">
          <site-logo />
        </factor-link>
      </div>
      <div class="footer-col">
        <h3 class="menu-header">Platform</h3>
        <factor-link path="https://factor.dev?ref=fiction">JavaScript CMS</factor-link>
      </div>
      <div class="footer-col">
        <h3 class="menu-header">Company</h3>
        <factor-link path="/careers">Careers</factor-link>
        <factor-link path="/contact">Contact Us</factor-link>
      </div>
      <div class="footer-col">
        <factor-link btn="primary" path="/careers">We're Hiring! &rarr;</factor-link>
        <div>
          <div class="copyright">
            <span>&copy; Fiction.com Inc.</span>
            <factor-link path="/terms-of-service">Terms</factor-link>
            <factor-link path="/privacy-policy">Privacy</factor-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { factorLink } from "@factor/ui"
export default {
  components: {
    factorLink,
    "site-logo": () => import("./logo.vue"),
  },
}
</script>

<style lang="less">
.content-footer {
  position: relative;
  width: 100%;
  max-width: var(--content-max-width);
  margin: 4em auto;
  padding: 0;
  .content-footer-pad {
    margin-top: 2em;
    padding: 0 2em 4em;
    display: grid;
    grid-template-columns: 1fr 1fr 2fr 1fr;
    grid-gap: 0;

    .footer-col {
      .pin {
        display: block;
        width: 35px;
        svg path {
          fill: #3a4854;
          opacity: 0.2;
        }
      }

      .menu-header {
        text-transform: uppercase;

        margin-bottom: 0.5rem;
      }
      a {
        display: block;

        color: inherit;

        line-height: 2em;
        cursor: pointer;
        text-decoration: none;
        transition: opacity 0.1s;
        &:hover {
          opacity: 1;
          color: var(--color-primary);
        }
        &.hiring {
          color: var(--color-secondary);
          opacity: 1;
          font-weight: 700;
          line-height: inherit;
        }
      }
      .copyright {
        margin-top: 4em;
        padding-bottom: 0.5em;
        span,
        a {
          font-size: 0.7em;
          opacity: 0.5;
          display: inline-block;
          margin-left: 5px;
        }
        a:hover {
          opacity: 1;
        }
      }
    }
  }
}
@media screen and (max-width: 700px) {
  .content-footer {
    .content-footer-pad {
      display: grid;
      grid-template-columns: 1fr;
      padding: 0 2em;
      .footer-col {
        padding-bottom: 2em;
      }
    }
  }
}
</style>
