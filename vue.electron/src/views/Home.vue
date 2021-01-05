<template>
  <div class="home">
    <q-card class="my-card">
      <div>
        现金
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input1"
            :key="i"
            v-model.number="input1[i]"
            type="number"
            outlined
            size="sm"
            style="max-width: 100px"
          />
          <q-input
            v-model="input1Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        微信
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input2"
            :key="i"
            v-model.number="input2[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input2Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            disable
            filled
            outlined
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        支付宝
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input3"
            :key="i"
            v-model.number="input3[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input3Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        内蒙卡
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input4"
            :key="i"
            v-model.number="input4[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input4Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        呼市卡
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input5"
            :key="i"
            v-model.number="input5[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input5Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        欠账
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input6"
            :key="i"
            v-model.number="input6[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input6Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        慢病做账
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input7"
            :key="i"
            v-model.number="input7[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input7Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        慢病购药
        <div class="q-gutter-md row items-start">
          <q-input
            v-for="(item, i) in input8"
            :key="i"
            v-model.number="input8[i]"
            type="number"
            outlined
            style="max-width: 100px"
          />
          <q-input
            v-model="input8Count"
            style="display: inline-block"
            color="grey-1"
            bg-color="light-blue-6"
            filled
            disable
            :input-style="{ color: '#fff', 'font-size': '20px' }"
          />
        </div>
      </div>
      <div>
        慢病差额
        <q-input
          v-model.number="input9Count"
          type="number"
          filled
          disable
          style="max-width: 200px"
        />
      </div>
      <div>
        <div class="q-gutter-md row items-start">
          <div>
            销售金额
            <q-input
              v-model.number="sellMony"
              type="number"
              filled
              style="max-width: 200px"
            />
          </div>
          <div>-</div>
          <div>
            实际金额统计
            <q-input
              v-model.number="practicalCountMony"
              type="number"
              filled
              disable
              style="max-width: 200px"
            />
          </div>
          <div>=</div>
          <div>
            金额情况
            <q-input
              v-model.number="resultMony"
              type="number"
              filled
              disable
              style="max-width: 200px"
            />
          </div>
          <div>
            结果:
            <span>{{ state }}</span>
          </div>
        </div>
      </div>
    </q-card>
  </div>
</template>

<script>
import round from 'lodash.round'
export default {
  name: 'Home',
  components: {},
  data() {
    return {
      sellMony: null,
      input1: [null, null, null, null, null, null, null, null],
      input2: [null, null, null, null, null, null, null, null],
      input3: [null, null, null, null, null, null, null, null],
      input4: [null, null, null, null, null, null, null, null],
      input5: [null, null, null, null, null, null, null, null],
      input6: [null, null, null, null, null, null, null, null],
      input7: [null, null, null, null, null, null, null, null],
      input8: [null, null, null, null, null, null, null, null],
      input9: [null, null, null, null, null, null, null, null]
    }
  },
  computed: {
    input1Count() {
      let count = 0
      this.input1.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input2Count() {
      let count = 0
      this.input2.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input3Count() {
      let count = 0
      this.input3.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input4Count() {
      let count = 0
      this.input4.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input5Count() {
      let count = 0
      this.input5.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input6Count() {
      let count = 0
      this.input6.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input7Count() {
      let count = 0
      this.input7.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input8Count() {
      let count = 0
      this.input8.map((item) => {
        if (item) {
          count += item
        }
      })
      return count
    },
    input9Count() {
      return round(this.input8Count - this.input7Count, 3)
    },
    practicalCountMony() {
      const count =
        this.input1Count +
        this.input2Count +
        this.input3Count +
        this.input4Count +
        this.input5Count +
        this.input6Count +
        this.input9Count
      return round(count, 3)
    },
    resultMony() {
      return this.sellMony - this.practicalCountMony
    },
    state() {
      return (
        (this.resultMony === 0 && '正好') ||
        (this.resultMony < 0 && '负值') ||
        (this.resultMony > 0 && '正值') ||
        '???'
      )
    }
  },
  mounted() {},
  methods: {
    initScale() {
      this.currentScale = 1
    },
    capture() {}
  }
}
</script>
<style lang="scss" scoped>

.home{
  display: flex;
  align-items: center;
  justify-content: center;
}
.my-card {
  padding: 10px;
  > div {
    padding: 10px;
    position: relative;
    border-bottom: 1px dashed #03a9f4;

  }
  > div:last-child {
    border-bottom: none
  }
}
</style>
