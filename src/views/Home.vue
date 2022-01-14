<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="WTF"/>
    <ui5-button id="openDialogButton" @click="onButtonClick()">ハッピーボタン</ui5-button>
    <ui5-dialog id="hello-dialog" header-text="CHOOSE">
      <p>ARE YOU HAPPY?</p>
      <div slot="footer" class="dialog-footer">
        <ui5-button id="closeDialogButton" @click="onClose">閉じる</ui5-button>
      </div>
      <ui5-button id="happyButton" @click="happy">ハッピーになる</ui5-button>
      <ui5-button id="unHappyButton" @click="unHappy">ハッピーにならない</ui5-button>
    </ui5-dialog>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import '@ui5/webcomponents/dist/Button'
import '@ui5/webcomponents/dist/Dialog'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      dialog: null
    }
  },
  methods: {
    onButtonClick () {
      this.dialog = document.getElementById('hello-dialog')
      this.dialog.show()
    },
    onClose () {
      this.dialog.close()
    },
    happy () {
      alert('HAPPYYYYYYYYYYYYYYYYYY!!!!!')
    },
    unHappy () {
      alert('UNHAPPYYYYYYYYYYYYYYYY!!!!!')
    }
  }
}
</script>

<style scoped lang='scss'>
ui5-button#closeDialogButton {
  width: 150px;
  background: rgb(151, 151, 151);
  font-weight: bold;
  color: white;
  border: none;
  margin: 4px;
}
ui5-button#happyButton {
  width: 150px;
  background: rgb(255, 70, 70);
  font-weight: bold;
  color: white;
  border: none;
  margin: 4px;
}
ui5-button#unHappyButton {
  width: 150px;
  background: rgb(37, 109, 255);
  font-weight: bold;
  color: white;
  border: none;
  margin: 4px;
  margin-left: 0px;
}
</style>
