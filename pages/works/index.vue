<script setup lang="ts"></script>

<template>
  <div class="p-4 md:p-8 max-w-250 m-auto">
    <h3 class="text-center mb-4">Past Works</h3>
    <section class="grid grid-cols-1 sm:grid-cols-2 gap-6">
      <ArchiveCard
        title="Old Portfolio Website"
        description="work.description"
        image="/images/oldworks/part-old-port.png"
        link="https://portfolio0223.netlify.app/"
        github="https://github.com/soe-ag/portfolio_2023feb"
      />

      <ArchiveCard
        title="Botha Competition Gallery Website"
        description="work.description"
        image="/images/oldworks/part-botha-gallery.png"
        link="https://lp.bo-tha.com/official_character_gallery/202212/"
        github="https://github.com/soe-ag/botha_compe_artlist"
      />
      <ArchiveCard
        title="Botha Official Website"
        description="work.description"
        image="/images/oldworks/part-botha.png"
        link="https://soe-ag.github.io/botha_about_clone/"
        github="https://github.com/soe-ag/botha_about_clone"
      />
      <ArchiveCard
        title="Botha Competition Website"
        description="work.description"
        image="/images/oldworks/part-botha-competition.png"
        link="https://soe-ag.github.io/botha_compete_clone/"
        github="https://github.com/soe-ag/botha_compete_clone"
      />
      <ArchiveCard
        title="Egodiva Marketing Website"
        description="work.description"
        image="/images/oldworks/part-egodia-marketing.png"
        link="https://soe-ag.github.io/egodiva_marketing_clone/"
        github="https://github.com/soe-ag/egodiva_marketing_clone"
      />
    </section>
  </div>
</template>
