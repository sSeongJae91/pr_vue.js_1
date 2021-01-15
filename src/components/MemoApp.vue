<template>
    <div class="memo-app">
        <memo-form/>
        <memo/>
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
  created () {
    this.memos = localStorage.memos ? JSON.parse(localStorage.memos) : []
  }
}
</script>
