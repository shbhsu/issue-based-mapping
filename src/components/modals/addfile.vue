<template>
      <div class="ui modal" id="addfile">
  <i class="close icon"></i>
  <div class="header">
新增議題相關文件
  </div>
  <div class="content">
  <div class="ui form">
    <div class="field">
    <label>檔案名稱</label>
    <input type="text" placeholder="檔案名稱" v-model="file.name">
  </div>
  <div class="field">
    <label>檔案網址</label>
    <input type="text" placeholder="檔案網址" v-model="file.address">
  </div>
  </div>
  </div>
  <div class="actions">
<!--     <div class="ui button">Cancel</div> -->
    <div class="ui primary button" v-on:click="addfile" id="ok">新增</div>
  </div>
</div>
</template>

<script>
import axios from 'axios'
import sidebar from '../sidebar'
import { setTimeout } from 'timers';
export default {
  name: 'addfile',
  components: {
    sidebar
  },
  data() {
    return {
      file: {
        name: '',
        address: ''
      }
    }
  },
  methods: {
    addfile: function () {
      $.ajax({
        url: "https://ethercalc.org/_/622t4v2804sk",
        type: 'POST',
        dataType: 'application/json',
        contentType: 'text/csv',
        processData: false,
        data: 'menu' + ',' + this.file.name + ',' + this.file.address
      }).then();
    }
  },
}
</script>
