<template>
  <a-layout-footer class="footer">
    <div class="footer-wrapper">
      <div class="footer__left">
        &copy; 2022
        <a href="https://mcloud.live" target="_blank">简会云</a>
        <sup>®</sup>
      </div>
      <div class="footer__right">
        <a-tooltip :content="$t('settings.language')">
          <a-button
            class="switch-btn"
            :shape="'circle'"
            @click="setDropDownVisible"
          >
            <template #icon>
              <icon-language />
            </template>
          </a-button>
        </a-tooltip>
        <a-dropdown position="top" @select="changeLocale">
          <div ref="triggerBtn" class="trigger-btn"></div>
          <template #content>
            <a-doption
              v-for="item in locales"
              :key="item.value"
              :value="item.value"
            >
              {{ item.label }}
            </a-doption>
          </template>
        </a-dropdown>
      </div>
    </div>
  </a-layout-footer>
</template>

<script lang="ts" setup>
  import { ref } from 'vue';
  import useLocale from '@/hooks/locale';
  import { LOCALE_OPTIONS } from '@/locale';

  const locales = [...LOCALE_OPTIONS];
  const { changeLocale } = useLocale();

  const triggerBtn = ref();
  const setDropDownVisible = () => {
    const event = new MouseEvent('click', {
      view: window,
      bubbles: true,
      cancelable: true,
    });
    triggerBtn.value.dispatchEvent(event);
  };
</script>

<style lang="less" scoped>
  .footer {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 40px;
    color: var(--color-neutral-4);
    text-align: center;

    &-wrapper {
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 100vw;
      margin: 0 40px 20px;
      padding: 10px;
    }

    &__right {
      > span {
        cursor: default;
      }
    }

    a {
      color: var(--color-neutral-4);
      text-decoration: none;
    }

    .switch-btn {
      color: rgb(var(--gray-8));
      font-size: 16px;
      border-color: rgb(var(--gray-2));
    }

    .trigger-btn {
      position: absolute;
      bottom: 44px;
      margin-left: 16px;
      background: #c00;
    }
  }
</style>
