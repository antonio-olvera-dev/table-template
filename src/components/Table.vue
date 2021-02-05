<template>
  <div class="tb-refactor">
    <!-- ---Menu--- -->
    <div class="tb-refactor__menu">
      <!-- ---Drop Down--- -->
      <div class="tb-refactor__menu__div1">
        <div class="tb-refactor__menu__div1__drop-down">
          <span> Show </span>
          <button
            class="tb-refactor__menu__div1__drop-down__btn"
            @focus="
              iconBool1 = true;
              openOptions(true);
            "
          >
            <span>
              {{ valueOptions }}
            </span>
            <i
              v-bind:class="{
                'tb-refactor__menudrop-down__icon-active': iconBool1,
              }"
              class="bi bi-chevron-down"
            ></i>
          </button>
        </div>
        <div class="tb-refactor__menu__div1__options" v-if="optionsBool">
          <ul class="tb-refactor__menu__div1__options__ul">
            <li class="id-options" @click="
              openOptions(false);
              iconBool1 = false;
              sendOption('10')" 
              v-bind:class="{'tb-refactor__menu__div1__options__ul__li-active': optionClass[0]}">10</li>
            <li class="id-options" @click="
              openOptions(false);
              iconBool1 = false;
              sendOption('20')" 
              v-bind:class="{'tb-refactor__menu__div1__options__ul__li-active': optionClass[1]}">20</li>
            <li class="id-options" @click="
              openOptions(false);
              iconBool1 = false;
              sendOption('30')" 
              v-bind:class="{'tb-refactor__menu__div1__options__ul__li-active': optionClass[2]}">30</li>
            <li class="id-options" @click="
              openOptions(false);
              iconBool1 = false;
              sendOption('40')" 
              v-bind:class="{'tb-refactor__menu__div1__options__ul__li-active': optionClass[3]}">40</li>
            <li class="id-options" @click="
              openOptions(false);
              iconBool1 = false;
              sendOption('50')" 
              v-bind:class="{'tb-refactor__menu__div1__options__ul__li-active': optionClass[4]}">50</li>
          </ul>
        </div>
      </div>
      <!-- ---Search--- -->
      <div class="tb-refactor__menu__div2">
        <input
          placeholder="Search..."
          class="tb-refactor__input__search"
          type="text"
        />
        <button class="btn" type="button">Add User</button>
      </div>
    </div>

    <!-- ---Table--- -->
    <table class="table tb-refactor__tb">
      <!-- ---Head--- -->
      <thead class="tb-refactor__tb__thead">
        <tr>
          <th scope="col">
            <div class="tb-refactor__tb__thead__div">
              <span>USER</span>
              <div class="tb-refactor__tb__thead__div__div-icon">
                <i class="bi bi-chevron-up"></i>
                <i class="bi bi-chevron-down"></i>
              </div>
            </div>
          </th>

          <th scope="col">
            <div class="tb-refactor__tb__thead__div">
              <span>EMAIL</span>
              <div class="tb-refactor__tb__thead__div__div-icon">
                <i class="bi bi-chevron-up"></i>
                <i class="bi bi-chevron-down"></i>
              </div>
            </div>
          </th>

          <th scope="col">
            <div class="tb-refactor__tb__thead__div">
              <span>ROLE</span>
              <div class="tb-refactor__tb__thead__div__div-icon">
                <i class="bi bi-chevron-up"></i>
                <i class="bi bi-chevron-down"></i>
              </div>
            </div>
          </th>

          <th scope="col">
            <div class="tb-refactor__tb__thead__div">
              <span>PLAN</span>
              <div class="tb-refactor__tb__thead__div__div-icon">
                <i class="bi bi-chevron-up"></i>
                <i class="bi bi-chevron-down"></i>
              </div>
            </div>
          </th>

          <th scope="col">
            <div class="tb-refactor__tb__thead__div">
              <span>STATUS</span>
              <div class="tb-refactor__tb__thead__div__div-icon">
                <i class="bi bi-chevron-up"></i>
                <i class="bi bi-chevron-down"></i>
              </div>
            </div>
          </th>

          <th scope="col">
            <div class="tb-refactor__tb__thead__div">
              <span>ACTION</span>
            </div>
          </th>
        </tr>
      </thead>

      <!-- ---Body--- -->
      <tbody
        class="tb-refactor__tb__tbody"
        v-for="(item, i) in [1, 2, 3, 4, 5, 6]"
        v-bind:key="i"
      >
        <tr>
          <td>{{ i }}</td>
          <td>sdfv</td>
          <td>Otto</td>
          <td>@mdo</td>
          <td>Otto</td>
          <td><i class="bi bi-three-dots-vertical"></i></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      iconBool1: false,
      optionsBool: false,
      valueOptions: "10",
      optionClass: { 0: true, 1: false, 2: false, 3: false, 4: false },
    };
  },
  methods: {
    openOptions(stat) {
      setTimeout(() => {
        this.optionsBool = stat;
      }, 100);
    },
    sendOption(num) {
      this.valueOptions = num;
      const table = document.getElementsByClassName("id-options");
      for (let i = 0; i < table.length; i++) {
        if (table[i].innerHTML == num) {
         this.optionClass[`${i}`] = true;
        } else {
         this.optionClass[`${i}`] = false;
        }
      }
    },
  },
};
</script>

<style lang="scss">
// ---Variables---
//-colors-
$c__hide: rgba(0, 0, 0, 0.2);
$c__default-light: rgb(223, 223, 223);
$c__default: rgb(168, 168, 168);
$c__default-dark: rgb(94, 94, 94);
$c__primary: #0da692;
$c__primary-light: #13ddc2;
$c__primary-dark: #0b7769;
$c__header-table: #f3f2f7;
//-Padding-
$pl__thead: 1.5em;
//---Reset---
.rst {
  padding: 0%;
  margin: 0%;
}

// ---Table---
.tb-refactor {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
  margin: 3em;
  border-radius: 0.3em;
  box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.2);

  .tb-refactor__menu {
    display: flex;
    flex-direction: row;
    width: 100%;
  }

  // ---Main---
  .tb-refactor__menu__div {
    display: flex;
    width: 50%;
    padding: 1em;
  }
  .tb-refactor__menu__div1 {
    @extend .tb-refactor__menu__div;
    flex-direction: column;
  }
  .tb-refactor__menu__div2 {
    @extend .tb-refactor__menu__div;
    justify-content: flex-end;
  }

  //---Drop Down---

  .tb-refactor__menu__div1__drop-down {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    user-select: none;
  }
  .tb-refactor__menu__div1__drop-down > span {
    color: $c__default-dark;
    margin-right: 0.5em;
  }
  .tb-refactor__menu__div1__drop-down__btn {
    @extend .tb-refactor__input;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    width: 4em;
    cursor: pointer;
    background-color: rgba(255, 105, 180, 0);
    height: 2em;
  }

  .tb-refactor__menu__div1__drop-down__btn > span {
    color: $c__default-dark;
    margin-right: 0.5em;
  }
  .tb-refactor__menu__div1__drop-down__btn > i {
    color: $c__default-dark;
    font-size: 0.8em;
    margin: 0.1em;
    margin-left: auto;

    transition-duration: 200ms;
  }
  .tb-refactor__menudrop-down__icon-active {
    transform: rotate(-180deg);
    transition-duration: 200ms;
  }
  //-Drop Down options-
  .tb-refactor__menu__div1__options {
    position: absolute;
    width: 4em;
    margin-top: 2.3em;
    margin-left: 3em;
    border-radius: 0.3em;
    background-color: white;
    box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.2);
    user-select: none;
  }
  .tb-refactor__menu__div1__options__ul {
    @extend .rst;
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    cursor: pointer;
  }
  .tb-refactor__menu__div1__options__ul > li {
    width: 100%;
    padding: 0.3em;
  }
  .tb-refactor__menu__div1__options__ul > li:first-child {
    border-top-right-radius: 0.3em;
    border-top-left-radius: 0.3em;
  }
  .tb-refactor__menu__div1__options__ul > li:last-child {
    border-bottom-right-radius: 0.3em;
    border-bottom-left-radius: 0.3em;
  }
  .tb-refactor__menu__div1__options__ul > li:hover {
    background-color: $c__header-table;
  }
  .tb-refactor__menu__div1__options__ul__li-active {
    background-color: $c__primary;
    color: white;
    &:hover {
      color: tomato;
    }
  }
  //--Button tb-refactor__menu__div2---
  .tb-refactor__menu__div2 > button {
    background-color: $c__primary;
    color: white;
    margin-left: 1em;
    transition-duration: 100ms;
  }
  .tb-refactor__menu__div2 > button:focus {
    box-shadow: none;
  }
  .tb-refactor__menu__div2 > button:hover {
    box-shadow: 0px 8px 15px 0px rgba(0, 0, 0, 0.2);
  }
  .tb-refactor__menu__div2 > button:active {
    box-shadow: none;
  }

  // ---Inputs---
  .tb-refactor__input {
    border-color: $c__default;
    border-style: solid;
    border-width: 0.1em;
    border-radius: 0.3em;
    outline: none;
    padding: 0.1em;
    padding-left: 0.5em;
    transition-duration: 200ms;
  }
  .tb-refactor__input:focus {
    border-color: $c__primary-light;
    border-width: 0.1em;
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.15),
      inset 0px 0px 3px 0px rgba(0, 0, 0, 0.1);
  }
  .tb-refactor__input:focus::placeholder {
    padding-left: 0.2em;
    transition-duration: 200ms;
  }
  .tb-refactor__input::placeholder {
    color: $c__hide;
    transition-duration: 200ms;
  }
  .tb-refactor__input__search {
    @extend .tb-refactor__input;
    width: 60%;
    padding-right: 1em;
  }

  // ---Thead---
  .tb-refactor__tb__thead {
    background-color: $c__header-table;
    text-align: start;
  }
  .tb-refactor__tb__thead > tr > th {
    padding-left: $pl__thead;
    cursor: pointer;
  }
  .tb-refactor__tb__thead__div {
    display: flex;
    align-content: center;
  }
  .tb-refactor__tb__thead__div > span {
    color: $c__default-dark;
    font-size: 0.8em;
  }
  .tb-refactor__tb__thead__div__div-icon {
    display: flex;
    flex-direction: column;
    margin-left: auto;
    color: $c__default;
  }
  .tb-refactor__tb__thead__div__div-icon > i {
    max-height: 1em;
    font-size: 0.6em;
  }

  //---Tbody---
  .tb-refactor__tb__tbody {
    text-align: start;
    border-width: 0.1em;
  }
  .tb-refactor__tb__tbody > tr > td {
    padding-left: $pl__thead;
  }
}
</style>
