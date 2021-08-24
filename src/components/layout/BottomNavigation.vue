<template>
  <nav class="nav">
    <div class="nav__link" v-for="(item, i) in links" :key="item">
      <a :href="links[i]" class="nav__link">
        <b-icon :icon="icons[i]" class="nav__icons"/>
        <span>{{menus[i]}}</span>
      </a>
    </div>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      links: ['#/', '#/about', '#/detail', '#/setting', '#/menus'],
      icons: ['house-fill', 'chat-left-dots-fill', 'graph-up', 'lightning-fill', 'list'],
      menus: ['홈', '문자열람', '상세분석', '예방팁', '메뉴'],
    }
  }
}
</script>
<style>
.nav {
  text-decoration: none;
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 55px;
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.2);
  background-color: #ffffff;
  display: flex;
  overflow-x: auto;
}

.nav__link {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  flex-grow: 1;
  min-width: 50px;
  overflow: hidden;
  white-space: nowrap;
  font-family: sans-serif;
  font-size: 13px;
  color: #444444;
  -webkit-tap-highlight-color: transparent;
  transition: background-color 0.1s ease-in-out;
}

.nav__link:hover {
  background-color: #eeeeee;
}

.nav__link--active {
  color: #009578;
}

.nav__icon {
  font-size: 18px;
}
</style>