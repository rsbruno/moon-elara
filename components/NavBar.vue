<template>
  <nav class="nav-bar-container">
    <div class="nav-bar-menu">
      <div class="nav-bar-logo"></div>
      <ul class="nav-bar-links">
        <li><a href="">início</a></li>
        <li><a href="">restaurantes</a></li>
        <li><a href="">mercados</a></li>
        <li><a href="">padarias</a></li>
        <li><a href="">farmácias</a></li>
      </ul>
    </div>
    <div class="nav-bar-search">
      <div class="nav-bar-input">
        <label for="search-input">
          <img src="~assets/icons/search.svg" />
        </label>
        <input id="search-input" placeholder="Busque por item ou loja" />
      </div>
    </div>
    <div class="nav-bar-icons">
      <h6>Dr. Luiz Libânio do Prado</h6>
      <button>
        <img src="~assets/icons/logout.svg" />
      </button>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.nav-bar-container {
  border-bottom: solid 1px #ddd;
  justify-content: space-between;
  align-items: center;
  position: relative;
  display: flex;
  height: 64px;
  width: 100%;
  box-shadow: inset 0 -1px 0 #dcdcdc;
  .nav-bar-menu {
    justify-content: space-between;
    align-items: center;
    display: flex;
    .nav-bar-logo {
      height: 100%;
      width: 150px;
    }
    .nav-bar-links {
      justify-content: space-between;
      align-items: center;
      display: flex;
      li {
        list-style: none;
        &:not(:first-child) {
          margin-left: 8px;
        }
        &:first-child {
          a {
            color: #7b1fa2;
            font-weight: 600;
          }
        }
        a {
          text-transform: capitalize;
          text-decoration: none;
          color: #717171;
          font-weight: 500;
        }
      }
    }
  }
  .nav-bar-search {
    width: 100%;
    padding: 0 20px;

    .nav-bar-input {
      border-radius: 4px;
      justify-content: flex-start;
      background: #f4f4f4;
      align-items: center;
      position: relative;
      margin-left: 5%;
      display: flex;
      width: 630px;
      height: 100%;

      img {
        margin-right: 12px;
        margin-left: 8px;
        resize: both;
        width: 24px;
      }
      input {
        background: transparent;
        outline: none;
        border: none;
        height: 44px;
        width: 100%;
      }
    }
  }
  .nav-bar-icons {
    justify-content: space-between;
    padding-right: 30px;
    align-items: center;
    position: relative;
    display: flex;
    width: 350px;
    h6 {
      font-size: 0.8rem;
    }
    button {
      background: transparent;
      outline: none;
      border: none;
      img {
        height: 30px;
        width: 30px;
      }
    }
  }
}
</style>