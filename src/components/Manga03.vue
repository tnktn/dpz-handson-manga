<template>
  <form @submit.prevent="handleSubmit" class="select-question">
    <dl>
      <dt>グランドフィナーレです。慎重にお選び下さい。</dt>
      <dd>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="04_01.gif">
          <span class="tx12px">安心のオチです</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="04_02.gif">
          <span class="tx12px">一年後…</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="04_03.gif">
          <span class="tx12px">視点を変えてみましょう</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="04_04.gif">
          <span class="tx12px">誰だ、きみ</span><br>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="04_z.gif">
          <span class="tx12px">スペシャル</span><br>
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
        koma3: this._koma
      }
    },
    methods: {
        handleSubmit(){
            this.$emit('next',{
                koma3: this._koma,
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