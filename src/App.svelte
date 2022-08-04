<script lang="ts">
	let name = "Hello"

	function handleClick() {
		name = "baba"
	}

	function sayHi() {
		return `${name}, World!`
	}

	let a = 1
	let b = 2
	let flag = false

	let h = "<h1 style='color: red;'>Hello</h1>"

	let color = "red"
	let foo = false
	let state = true
	let count = 1
	setTimeout(() => {
		color = "blue"
		foo = true
		state = false
		count++
	}, 1000)

	let list = ["a", "b", "c", "d", "e", "f"]
	let list1 = [{ name: "雷猴" }, { name: "鲨鱼辣椒" }]
	let list2 = []
</script>

<!-- 插值 -->
<main>
	<div>Hello, {name}</div>
	<button on:click={handleClick}>改名啰!</button>
</main>
<!-- 表达式 -->
<div>{sayHi()}</div>
<div>{a} + {b} = {a + b}</div>
<div>{flag ? "haha" : "heihei"}</div>

<!-- 属性绑定 -->
<div title={name}>属性绑定</div>

<!-- 渲染 HTML 标签 @html -->
<div>{@html h}</div>

<!-- 行内样式 style -->
<div style="color: {color}">Hello</div>

<!-- 绑定 class -->
<div class:active={foo}>heihei</div>

<!-- 基础条件判断 -->
<!-- 使用 {#if} 开头，{/if} 结尾。 -->

<!-- {#if 条件判断}
...
{/if} -->

{#if state}
	<div>hahahaha</div>
{/if}

<!-- 两种条件 -->
<!-- {#if 条件判断}
...
{:else}
...
{/if} -->
{#if state}
	<div>hehe</div>
{:else}
	<div>heihei</div>
{/if}

<!-- 多种条件 -->

<!-- {#if 条件判断}
...
{:else if 条件判断}
...
{/if} -->
{#if count === 1}
	<div>雷猴</div>
{:else if count === 2}
	<div>鲨鱼辣椒</div>
{:else}
	<div>蟑螂恶霸</div>
{/if}

<!-- 列表渲染 #each -->

<!-- 如果你有一堆数据需要展示出来，可以使用 #each 方法。

使用 {#each} 开头，{/each} 结尾。 -->

<!-- 遍历数组 -->

<!-- {#each expression as name}
...
{/each} -->
<ul>
	{#each list as item}
		<li>{item}</li>
	{/each}
</ul>

<!-- 遍历数组（带下标） -->
<ul>
	{#each list as item, index}
		<li>{item}---{index}</li>
	{/each}
</ul>

<!-- 如果元素是对象，可以解构 -->
<ul>
	{#each list1 as { name }}
		<li>{name}</li>
	{/each}
</ul>

<!-- 默认内容 -->
<div>
	{#each list2 as { name }}
		<div>{name}</div>
	{:else}
		<div>暂无数据</div>
	{/each}
</div>

<style>
	.active {
		color: skyblue;
	}
</style>
