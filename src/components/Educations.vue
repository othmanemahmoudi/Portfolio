<template>
    <section id="formations" class=" flex flex-col items-center justify-center pt-20">

        <div class="flex flex-col items-center justify-center bg-white mb-12">
    <!-- Titre -->
    <h2 class="text-4xl font-bold text-[#CFAF71]">
      Mon Parcours Académique
    </h2>

    <!-- Stepper -->
    <div class="stepper-box">
      <div class="stepper-step stepper-completed">
        <div class="stepper-circle">✓</div>
        <div class="stepper-line"></div>
        <div class="stepper-content">
          <div class="stepper-title">Baccalauréat Scientifique</div>
          <div class="stepper-status">Terminé</div>
          <div class="stepper-time">2017 - 2020</div>
        </div>
      </div>
      <div class="stepper-step stepper-completed">
        <div class="stepper-circle">✓</div>
        <div class="stepper-line"></div>
        <div class="stepper-content">
          <div class="stepper-title">Baccalauréat Scientifique</div>
          <div class="stepper-status">Terminé</div>
          <div class="stepper-time">2017 - 2020</div>
        </div>
      </div>
            <div class="stepper-step stepper-completed">
        <div class="stepper-circle">✓</div>
        <div class="stepper-line"></div>
        <div class="stepper-content">
          <div class="stepper-title">Baccalauréat Scientifique</div>
          <div class="stepper-status">Terminé</div>
          <div class="stepper-time">2017 - 2020</div>
        </div>
      </div>
    </div>
  </div>

    </section>
</template>

<script setup>
</script>

<style scoped>
.stepper-box {
  background-color: white;
  padding: 32px;
  width: 420px;
}

.stepper-step {
  display: flex;
  margin-bottom: 48px; /* plus d’espace entre les formations */
  position: relative;
}

.stepper-step:last-child {
  margin-bottom: 0;
}

.stepper-line {
  position: absolute;
  left: 19px;
  top: 40px;
  bottom: -60px;
  width: 2px;
  background: linear-gradient(to bottom, #CFAF71, #FFECC2, #8B6937);
  z-index: 1;
}

.stepper-step:last-child .stepper-line {
  display: none;
}

.stepper-circle {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 16px;
  z-index: 2;
  font-weight: bold;
}

/* États */
.stepper-completed .stepper-circle {
  background: linear-gradient(to right, #CFAF71, #8B6937);
  color: white;
}

.stepper-title {
  font-weight: 600;
  margin-bottom: 10px;

}

.stepper-completed .stepper-title {
  color: #8B6937;
}

.stepper-active .stepper-title {
  color: #CFAF71;
}

.stepper-pending .stepper-title {
  color: #8B6937;
  opacity: 0.6;
}

.stepper-status {
  font-size: 13px;
  display: inline-block;
  padding: 2px 8px;
  border-radius: 12px;
  margin-top: 4px;
}

.stepper-completed .stepper-status {
  background-color: #FFECC2;
  color: #8B6937;
}

.stepper-active .stepper-status {
  background-color: #CFAF71;
  color: white;
}

.stepper-time {
  font-size: 12px;
  color: #8B6937;
}
</style>
