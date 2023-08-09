<template>
    <div class="navbar bg-base-100">
        <div class="flex-1">
          <a class="btn btn-ghost normal-case text-xl">Edy Nogueira</a>
        </div>
        <div class="flex-none">
          <ul class="menu menu-horizontal px-1">
            
            <li>
              <details>
                <summary>
                  Social Links
                </summary>
                <ul class="p-2 bg-base-100">
                  <li><a href="https://www.instagram.com/edypnog/">Instagram</a></li>
                  <li><a href="https://github.com/edypnog">GitHub</a></li>
                  <li><a href="https://www.linkedin.com/in/edypnog/">LinkedIn</a></li>
                </ul>
              </details>
            </li>
            <li><a :href="emailLink">Contact</a></li>
            <!-- <LanguageSwitcher /> -->
          </ul>
        </div>
      </div>
</template>

<script>
export default {

  data() {
    return {
      emailAddress: 'edypnog@gmail.com',
    }
  },
  computed: {
    emailLink() {
      return `mailto:${this.emailAddress}`;
    }
  }

}


</script>