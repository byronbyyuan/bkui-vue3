<template>
  <bk-popover
    content="文字提示"
    placement="bottom"
    @after-hidden="handleHide"
    @after-show="handleShow"
  >
    <bk-button>自定义回调函数</bk-button>
  </bk-popover>
</template>

<script setup>
  import BkMessage from '@bkui-vue/message';

  const handleShow = () => {
    BkMessage({
      theme: 'success',
      message: 'onShow',
    });
  };

  const handleHide = () => {
    BkMessage({
      theme: 'error',
      message: 'onClose',
    });
  };
</script>
