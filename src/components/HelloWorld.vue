<template>
  <div class="hello">
    <div class="header">
      <h2><img :src="brannerImag"></h2>
    </div>
    <div class="list__wrapper">
      <ul class="list">
        <li v-for="(item, key) in items" :key="key">
          <div class="li-img"><img :src="item.imgSrc"></div>
          <div class="li-content">
            <div class="product-title">{{ item.poductName }}</div>
            <div class="product-price">
              <span class="tag">双11价</span><span class="price">{{ item.price }}</span>
            </div>
            <div class="product-tips">{{ item.activityType }}</div>
          </div>
          <a href="" class="go">{{ item.activeName }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  mounted () {
    import('../../data.json').then(res => {
      console.log(res)
      let {brannerImag, items} = res.sections[0]
      this.brannerImag = brannerImag
      this.items = items
    })
  },
  data () {
    return {
      brannerImag: '',
      items: ''
    }
  }
}
</script>
<<style lang="scss" scoped>
@import '../style/mixin.scss';
</style>
