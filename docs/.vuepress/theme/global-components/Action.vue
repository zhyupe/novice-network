<template>
  <strong
    :data-ck-action-id="id"
    :data-ck-action-name="name"
    :data-ck-action-job-id="jobId"
  >
    <slot>{{ name }}</slot>
  </strong>
</template>

<script>
const jobList = {
  冒险者: 0,
  剑术师: 1,
  格斗家: 2,
  斧术师: 3,
  枪术师: 4,
  弓箭手: 5,
  幻术师: 6,
  咒术师: 7,
  刻木匠: 8,
  锻铁匠: 9,
  铸甲匠: 10,
  雕金匠: 11,
  制革匠: 12,
  裁衣匠: 13,
  炼金术士: 14,
  烹调师: 15,
  采矿工: 16,
  园艺工: 17,
  捕鱼人: 18,
  骑士: 19,
  武僧: 20,
  战士: 21,
  龙骑士: 22,
  吟游诗人: 23,
  白魔法师: 24,
  黑魔法师: 25,
  秘术师: 26,
  召唤师: 27,
  学者: 28,
  双剑师: 29,
  忍者: 30,
  机工士: 31,
  暗黑骑士: 32,
  占星术士: 33,
  武士: 34,
  赤魔法师: 35,
  青魔法师: 36,
  绝枪战士: 37,
  舞者: 38
}

export default {
  props: {
    name: String,
    id: {
      type: Number,
      default: null
    },
    job: {
      type: String,
      default: ''
    }
  },
  data: function() {
    return {}
  },
  computed: {
    jobId() {
      if (this.job) {
        return jobList[this.job]
      }
      if (
        this.$page &&
        this.$page.frontmatter &&
        this.$page.frontmatter.jobName
      ) {
        return jobList[this.$page.frontmatter.jobName]
      }
      return null
    }
  }
}
</script>