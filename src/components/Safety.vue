<script setup>
import anime from 'animejs'
import { onMounted } from 'vue'
import SafetyBlock from './SafetyBlock.vue'

onMounted(() => {
  const textWrapper = document.querySelector('.safetyHeadText')
  textWrapper.innerHTML = textWrapper.textContent.replace(/\S/g, "<span class='letter'>$&</span>");
  anime.timeline({ loop: false })
    .add({
      targets: '.safetyHeadText .letter',
      opacity: [0, 1],
      fontSize: [0, '5rem'],
      duration: 1000,
      easing: "easeOutExpo",
      delay: (el, i) => 80 * (i + 3)
    })
    anime({
      targets: '.safetyBlock',
      opacity: [0, 1],
      duration: 1000,
      easing: "easeOutExpo",
      delay: (el, i) => 80 * (i + 3)

    })
})


</script>

<template>
  <div class="safetyHead">
    <h1 class="safetyHeadText">Safety/Terms</h1>
  </div>
  <div class="safetyBlocks">
    <SafetyBlock
      title="Harrassment Policy⚠️"
      text="<p>We are committed to providing a safe and secure environment for all of our users. We have a zero-tolerance policy for any form of harassment or abuse. If you are experiencing any form of harassment or abuse, please contact us immediately at <a href='mailto:lumey@lumey.dev'>lumey@lumey.dev</a></p>"
    />
    <SafetyBlock
      title="Privacy 🔒"
      text="<p>Most lumey services do not collect user data. Some services, such as <a href='card.lumey.dev'>card.lumey.dev</a> collect anonymous analytics. Other services, such as Nextcloud, can collect a lot of data. Our privacy policy spans all of our services, but does not mean each one collects the same amount of data. You can view the policy at <a href='privacy.lumey.dev'>privacy.lumey.dev</a></p>"
    />
    <SafetyBlock
      title="Don't:"
      text="<ul><li>Use lumey services for any illegal activity.</li> <li>Use lumey services to harass or abuse anyone.</li> <li>Use lumey services to distribute malware, spam, or illegal content.</li></ul>"
    />
    <SafetyBlock
      title="Do:"
      text="<ul><li>Use lumey services for good.</li> <li>Use lumey services to help others.</li> <li>Use lumey services to make the world a better place. ♥️</li></ul>"
    />
    

  </div>
</template>

<style scoped>
.safetyHead {
  font-size: 5rem;
  font-weight: 700;
  margin-top: 5rem;
  color: white;
  align-items: center;
  text-align: center;
  font-family: DM Sans;
  font-weight: 700;
}

.safetyBlocks {
  display: block;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-left: 10rem;
  margin-right: 10rem;
  padding-top: 1rem;
  padding-bottom: 1rem;
}


</style>
