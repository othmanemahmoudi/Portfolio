<template>
  <section id="formations" class="flex flex-col items-center justify-center pt-20 bg-white">
    <div class="flex flex-col items-center justify-center mb-12">
      <!-- Titre -->
      <h2 class="text-4xl font-bold text-[#CFAF71] mb-16 animate-fadeIn">
        Mon Parcours Académique
      </h2>

      <!-- Stepper -->
      <div class="stepper-box">
        <div class="stepper-step stepper-completed">
          <div class="stepper-circle animate-pulse">✓</div>
          <div class="stepper-line animate-line"></div>
          <div class="stepper-content animate-step">
            <div class="stepper-title">Baccalauréat Scientifique</div>
            <div class="stepper-status">Terminé</div>
            <div class="stepper-time">2017 - 2020</div>
          </div>
        </div>

        <div class="stepper-step stepper-completed">
          <div class="stepper-circle animate-pulse">✓</div>
          <div class="stepper-line animate-line"></div>
          <div class="stepper-content animate-step delay-200">
            <div class="stepper-title">Licence Informatique</div>
            <div class="stepper-status">Terminé</div>
            <div class="stepper-time">2020 - 2023</div>
          </div>
        </div>

        <div class="stepper-step stepper-completed">
          <div class="stepper-circle animate-pulse">✓</div>
          <div class="stepper-content animate-step delay-400">
            <div class="stepper-title">Master Informatique</div>
            <div class="stepper-status">En cours</div>
            <div class="stepper-time">2023 - 2025</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.stepper-box {
  background-color: white;
  padding: 32px;
  width: 420px;
}

.stepper-step {
  display: flex;
  margin-bottom: 48px;
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
  transform-origin: top; /* la ligne grandit depuis le cercle */
}

/* Cercle */
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
.stepper-completed .stepper-circle {
  background: linear-gradient(to right, #CFAF71, #8B6937);
  color: white;
}

/* Animations */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fadeIn {
  animation: fadeIn 2s ease forwards;
}

@keyframes step {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-step {
  animation: step 2s ease forwards;
}
.delay-200 { animation-delay: 0.5s; }
.delay-400 { animation-delay: 1s; }

@keyframes lineGrow {
  from { transform: scaleY(0); }
  to { transform: scaleY(1); }
}
.animate-line {
  animation: lineGrow 2s ease forwards;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(207,175,113,0.6); }
  50% { transform: scale(1.1); box-shadow: 0 0 15px 5px rgba(207,175,113,0.3); }
}
.animate-pulse {
  animation: pulse 2s infinite;
}
</style>
