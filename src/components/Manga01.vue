<template>
  <form @submit.prevent="handleSubmit" class="select-question">
    <dl>
      <dt>べつやくが歩いていたら、タコにあいました。どう話しかけましょう。</dt>
      <dd>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="02_01.gif" required>
          <span class="tx12px">普通に</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="02_02.gif" required>
          <span class="tx12px">まずは自己紹介</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="02_03.gif" required>
          <span class="tx12px">丁寧な感じで</span>
        </label>
        <label>
          <input v-model="_koma" type="radio" name="t2" value="02_04.gif" required>
          <span class="tx12px">テレパシーを駆使</span><br>
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
        koma1: this._koma
      }
    },
    methods: {
        handleSubmit(){
            this.$emit('next',{
                koma1: this._koma,
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