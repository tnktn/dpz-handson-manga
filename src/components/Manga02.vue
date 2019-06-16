<template>
  <form @submit.prevent="handleSubmit" class="select-question">
    <dl>
      <dt>もっとタコと会話しましょう。</dt>
      <dd>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="03_01.gif">
          <span class="tx12px">許可を求められる</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="03_02.gif">
          <span class="tx12px">無謀なことをいわれてみる</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="03_03.gif">
          <span class="tx12px">間違った英語の教科書のように</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="03_04.gif">
          <span class="tx12px">うそでもついてみましょう</span><br>
        </label>
      </dd>
    </dl>
    <button>次へ</button>
  </form>
</template>

<script>
export default {
    data(){
      return {
        koma2: this._koma
      }
    },
    methods: {
        handleSubmit(){
            this.$emit('next',{
                koma2: this._koma,
            })
        }
    }
}
</script>


<style scoped>
.select-question {
  margin-bottom: 24px;
  padding-bottom: 24px;
  border-bottom: dotted 1px #c6c6c6;
}

dd {
  margin: 16px 0 0;
  padding: 0 0 8px 0;
}

button {
  width: 60px;
}

input[type='text'] {
  margin-right: 20px;
}

label {
  display: block;
}
</style>