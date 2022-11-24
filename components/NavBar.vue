<template>
  <nav class="nav-bar-container">
    <div class="nav-bar-logo"></div>
    <div class="nav-bar-links">
      <button class="nav-bar-default-link">
        início <font-awesome-icon :icon="['fa-solid', 'chevron-down']" />
      </button>
      <ul>
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
      <font-awesome-icon :icon="['fa-solid', 'chevron-down']" />
      <button>
        <img src="~assets/icons/logout.svg" />
      </button>
    </div>

    <div class="nav-bar-hamburger">
      <button>
        <font-awesome-icon :icon="['fa', 'bars']" />
      </button>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.nav-bar-container {
  grid-template-areas: "logo menu search icons";
  grid-template-columns: 150px 450px 1fr 250px;
  box-shadow: inset 0 -1px 0 #dcdcdc;
  border-bottom: solid 1px #ddd;
  justify-content: space-between;
  align-items: center;
  position: relative;
  display: grid;
  height: 64px;
  width: 100%;

  @media (max-width: 1360px) {
    grid-template-columns: 150px auto 1fr 250px;
  }

  @media (max-width: 940px) {
    grid-template-columns: 150px 1fr 220px;
    grid-template-rows: 1fr 1fr;
    grid-template-areas:
      "logo menu icons"
      "search search search";
    height: 108px;
    padding: 8px;
  }

  @media (max-width: 810px) {
    grid-template-areas: "logo search hamburger";
    grid-template-columns: 150px 1fr 50px;
    grid-template-rows: 1fr;
    height: 60px;
    padding: 8px;
  }

  @media (max-width: 610px) {
    grid-template-areas: "logo hamburger" "search search";
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    padding: 8px;
    height: 108px;
  }

  .nav-bar-logo {
    height: 100%;
    grid-area: logo;
  }

  .nav-bar-links {
    justify-content: space-between;
    align-items: center;
    display: flex;
    grid-area: menu;
    height: 100%;
    position: relative;

    @media (max-width: 810px) {
      display: none;
    }

    .nav-bar-default-link {
      justify-content: flex-start;
      text-transform: capitalize;
      background: transparent;
      align-items: center;
      color: #7b1fa2;
      font-weight: 600;
      cursor: pointer;
      font-size: 1rem;
      padding: 0 12px;
      display: flex;
      outline: none;
      height: 100%;
      border: none;

      svg {
        margin-left: 12px;
      }

      @media (min-width: 1360px) {
        display: none;
      }

      @media (max-width: 940px) {
        display: none;
      }
    }

    ul {
      justify-content: space-between;
      align-items: center;
      display: flex;
      height: 100%;
      gap: 8px;

      @media (min-width: 941px) and (max-width: 1360px) {
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
        border-bottom-right-radius: 4px;
        border-bottom-left-radius: 4px;
        align-items: flex-start;
        flex-direction: column;
        height: min-content;
        position: absolute;
        padding: 12px;
        width: 300px;
        top: 100%;
      }

      @media (max-width: 940px) {
        justify-content: flex-start;
        flex-direction: row;
        position: relative;
        width: 100%;
        gap: 8px;
      }

      li {
        list-style: none;

        &:nth-child(1) {
          a {
            color: #7b1fa2;
            font-weight: 600;
          }
        }

        a {
          transition: all ease 400ms;
          text-transform: capitalize;
          text-decoration: none;
          color: #717171;
          font-weight: 500;

          &:hover {
            color: #00a296;
          }
        }
      }
    }
  }
  .nav-bar-search {
    grid-area: search;
    padding: 8px 20px;
    height: 100%;
    width: 100%;

    @media (max-width: 940px) {
      padding: 0;
    }

    .nav-bar-input {
      border-radius: 4px;
      justify-content: flex-start;
      background: #f4f4f4;
      align-items: center;
      position: relative;
      min-width: 400px;
      margin-left: 5%;
      max-width: 60%;
      display: flex;
      height: 100%;
      width: 100%;

      @media (max-width: 1360px) {
        max-width: 90%;
      }

      @media (max-width: 940px) {
        max-width: 100%;
        margin-left: 0;
      }

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
    grid-area: icons;
    display: flex;
    height: 100%;

    @media (max-width: 940px) {
      padding-right: 0;
    }

    @media (max-width: 810px) {
      display: none;
    }

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

  .nav-bar-hamburger {
    grid-area: hamburger;
    display: none;
    height: 100%;

    button {
      justify-content: space-between;
      background: transparent;
      align-items: center;
      outline: none;
      display: flex;
      height: 100%;
      border: none;
      width: 100%;

      svg {
        color: #7b1fa2;
        margin-left: 8px;
        height: 30px;
        width: 30px;
      }

      @media (max-width: 610px) {
        height: 40px;
        width: 40px;
      }
    }

    @media (max-width: 810px) {
      display: block;
    }

    @media (max-width: 610px) {
      justify-content: flex-end;
      display: flex;
    }
  }
}
</style>