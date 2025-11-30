<script>
  const actionItems = {
    "Quick Links": [
      { label: "Gmail", href: "https://gmail.com" },
      {
        label: "DouxDolci Hosting",
        href: "https://douxdolci-hosting.net:10000/",
      },
    ],
    Projects: [
      {
        label: "Best Paws",
        href: "https://bestpawsontherun.com/",
        actions: [
          { label: "Admin", href: "https://bestpawsontherun.com/wp-admin/" },
          { label: "Website", href: "https://bestpawsontherun.com/" },
        ],
      },
      {
        label: "STSS Inc.",
        href: "https://stssinc.com/",
        actions: [
          { label: "Admin", href: "https://stssinc.com/wp-admin/" },
          { label: "Website", href: "https://stssinc.com/" },
        ],
      },
      {
        label: "mEducation Alliance",
        href: "https://meducationalliance.org/",
        actions: [
          { label: "Admin", href: "https://meducationalliance.org/wp-admin/" },
          { label: "Website", href: "https://meducationalliance.org/" },
        ],
      },
    ],
  };
</script>

<div
  class="w-full relative bg-gray-50 min-h-screen p-8"
  style="background-image: url(https://picsum.photos/1920/1080); background-size: cover; background-position: center;"
>
  <!-- subtle off-white overlay to keep the bordered look readable -->
  <div class="absolute inset-0 bg-black/40 pointer-events-none"></div>

  <div class="relative z-10">
    <div class="flex justify-end mb-4"></div>
    {#each Object.entries(actionItems) as [section, items]}
      <section class="fade-in mb-12">
        <h2 class="text-4xl font-bold text-[#ececec] mb-6">
          {section}
        </h2>
        <div class="flex flex-wrap gap-6">
          {#each items as item, index}
            <div
              class="w-86 bg-[#ececec] rounded-lg overflow-hidden border-2 border-gray-900"
              transition:slide={{ duration: 300, delay: index * 50 }}
            >
              <a
                href={item.href}
                target="_blank"
                class="flex items-center p-6 text-gray-900 hover:opacity-80 transition-opacity"
              >
                <span class="text-2xl font-semibold">{item.label}</span>
              </a>
              {#if item.actions && item.actions.length > 0}
                <div class="p-4 border-t-2 border-gray-900">
                  <p
                    class="text-xs text-gray-600 mb-3 font-semibold uppercase tracking-wide"
                  >
                    Actions
                  </p>
                  <div class="flex flex-col gap-2">
                    {#each item.actions as action}
                      <a
                        href={action.href}
                        target="_blank"
                        class="px-3 py-2 bg-gray-50 border border-gray-900 hover:bg-gray-900 hover:text-gray-50 text-gray-900 text-sm font-medium rounded transition-colors text-center"
                      >
                        {action.label}
                      </a>
                    {/each}
                  </div>
                </div>
              {/if}
            </div>
          {/each}
        </div>
      </section>
    {/each}
  </div>
</div>

<style>
  .fade-in {
    opacity: 0;
    animation: fadeInAnimation 0.8s forwards;
  }

  @keyframes fadeInAnimation {
    to {
      opacity: 1;
    }
  }
</style>
