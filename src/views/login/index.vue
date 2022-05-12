<template>
  <div class="container">
    <header class="header">
      <div class="logo">
        <img src="/src/assets/images/logo-mcloud-mix.svg" />
      </div>
      <div class="nav">
        <a-link href="/" :hoverable="false">
          {{ $t('settings.nav.home') }}
        </a-link>
        <a-link href="/" :hoverable="false">
          {{ $t('settings.nav.useGuide') }}
        </a-link>
      </div>
    </header>

    <div class="content">
      <div class="scan-qrcode">
        <div class="box-qrcode">
          <img src="/src/assets/images/qrImg.png" width="160" height="160" />
          <!--<wechat-login
            :app-id="sns.wechat.appId"
            :redirect-uri="sns.wechat.callback"
            :visible="model.loginType==='wechat'"
            :self-redirect="true"
            @login="wechatlogin"
          />-->
        </div>
        <div class="tips">
          {{ $t('login.form.scanWxQrCode') }}
        </div>
        <div class="question">
          {{ $t('login.form.problem') }}
          <a-link>
            {{ $t('login.form.customerService') }}
          </a-link>
        </div>
      </div>
      <LoginForm class="login-form-cpt" />
    </div>
    <div class="footer">
      <Footer />
    </div>
  </div>
</template>

<script lang="ts" setup>
  import Footer from '@/components/footer/index.vue';
  import LoginForm from './components/login-form.vue';
</script>

<style lang="less" scoped>
  body[arco-theme='dark'] {
    .container {
      background-image: none;
    }
  }

  .container {
    display: flex;
    flex-direction: column;
    height: 100vh;
    min-height: 600px;
    background: url('/src/assets/images/bg.jpg') no-repeat fixed;
    background-size: 100% 100%;

    .header {
      display: flex;
      justify-content: space-between;
      width: 100vw;
      height: 80px;
      background-color: var(--white-alpha);

      .logo {
        display: block;
        align-items: center;
        width: 128px;
        height: 40px;
        margin: 20px 40px;
      }

      .nav {
        display: flex;
        margin-right: 40px;

        a {
          display: flex;
          align-items: center;
          justify-content: center;
          height: 100%;
          padding: 20px;
          color: var(--color-text-4);
          font-weight: bold;
          line-height: 100%;
        }
      }
    }

    .content {
      position: relative;
      top: 100px;
      left: calc(50% - 350px);
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      width: 660px;
      height: 400px;
      background-color: var(--white-alpha);

      .scan-qrcode {
        display: inline-block;
        width: 280px;
        margin: 40px 0;
        text-align: center;
        border-right: 1px solid rgba(var(--gray-10), 0.05);

        .box-qrcode {
          width: 100%;
          margin-top: 26px;
        }

        .tips {
          width: 200px;
          margin: 31px auto;
          padding: 10px;
          color: var(--color-text-2);
          font-weight: 400;
          background-color: rgba(var(--gray-10), 0.15);
          border-radius: 100px;
          box-shadow: inset 2px 3px 2px -2px rgba(var(--gray-10), 0.25);
        }
      }

      .question {
        margin-top: 40px;
        padding: 0 20px;
        color: rgb(var(--gray-8));
      }

      .login-form-cpt {
        width: 300px;
      }
    }

    .footer {
      position: relative;
      top: 100px;
      width: 100%;
    }
  }
</style>

<style lang="less" scoped>
  // responsive
  @media (max-width: @screen-lg) {
    .container {
      .banner {
        width: 25%;
      }
    }
  }
</style>
