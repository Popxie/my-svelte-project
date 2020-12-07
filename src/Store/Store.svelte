<script>
  import { onDestroy } from 'svelte'
  import { count } from './stores.js'
  import Decrementer from './Decrementer.svelte'
  import Incrementer from './Incrementer.svelte'
  import Resetter from './Resetter.svelte'
  
  let count_value
  // 手动订阅
  const unsubscribe = count.subscribe(value => {
		count_value = value;
  })
  // 防止内存泄漏
  onDestroy(unsubscribe)
</script>

<div>
  <!-- 手动订阅 -->
  <h1>The count is {count_value}</h1>
  <!-- 自动订阅 简写（自动订阅仅适用于在组件的顶级作用域声明(或导入)的存储变量） -->
  <h1>The count is {$count}</h1>
  <Decrementer />
  <Incrementer />
  <Resetter />
</div>
