<template>
  <div>
    <h3>空数据</h3>
    <div style="width: 100%; height: 300px">
      <bk-table
        :columns="columns"
        :data="[]"
        empty-text="没有数据"
      />
    </div>
    <h3>过滤为空-试试过滤来源为 Email</h3>
    <div style="width: 100%; height: 300px">
      <bk-table
        :border="['outer']"
        :columns="columns"
        :data="tableData"
        empty-text="没有数据"
      />
    </div>
    <h3>自定义空数据-empty插槽</h3>
    <div style="width: 100%; height: 300px">
      <bk-table
        :columns="columns"
        :data="[]"
      >
        <template #empty>
          <div :style="emptyTextStyle">EMPTY</div>
        </template>
      </bk-table>
    </div>
  </div>
</template>

<script>
  import { defineComponent } from 'vue';

  import { DATA_COLUMNS, DATA_TABLE } from './options';
  export default defineComponent({
    components: {},
    data() {
      return {
        columns: [...DATA_COLUMNS],
        activeRowInfo: {},
        tableData: [...DATA_TABLE],
      };
    },
    computed: {
      emptyTextStyle() {
        return 'width: 100%; height: 100px; display: flex; justify-content: center; align-items: center; font-size: 30px;';
      },
    },
  });
</script>
