<template>
    <div class="memo-app">
        <memo-form @addMemo="addMemo"/>
        <ul class="memo-list">
            <memo v-for="memo in memos"
                :key="memo.id"
                :memo="memo"/>
        </ul>
    </div>
</template>
<script>
import MemoForm from './MemoForm'
import Memo from './Memo'

export default {
  name: 'MemoMapp',
  components: {
    MemoForm,
    Memo
  },
  data () {
    return {
      memos: []
    }
  },
  methods: {
    addMemo (payload) {
      this.memos.push(payload)
      this.storesMemo()
    },
    storesMemo () {
      const memosToString = JSON.stringify(this.memos)
      localStorage.setItem('memos', memosToString)
    }
  },
  created () {
    this.memos = localStorage.memos ? JSON.parse(localStorage.memos) : []
  }
}
</script>
<style scoped>
    .memo-list {
        padding: 20px 0;
        margin: 0;
    }
</style>
