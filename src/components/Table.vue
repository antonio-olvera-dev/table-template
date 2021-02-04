<template>
  <div class="tb-refactor">
    <!-- ---Menu--- -->
    <div class="tb-refactor__menu">
      <div class="tb-refactor__menu__div1">
        <div class="tb-refactor__menu__div1__div-input">
          <span> Show </span>
          <!-- TODO  Work autocomplete-->
          <input
            @focus="iconBool1 = true"
            @blur="iconBool1 = false"
            placeholder="10"
            class="tb-refactor__input__pag"
            type="text"
          />
          <i
            v-bind:class="{
              'tb-refactor__menu__div1__div-input_icon-active': iconBool1,
            }"
            class="bi bi-chevron-down"
          ></i>
        </div>
      </div>
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
          <th scope="col">#</th>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Handle</th>
        </tr>
      </thead>

      <!-- ---Body--- -->
      <tbody class="tb-refactor__tb__tbody">
        <tr>
          <td scope="row">1</td>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
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
    };
  },
};
</script>

<style lang="scss">
// ---Variables---
//-colors-
$c__hide: rgba(0, 0, 0, 0.2);
$c__default: rgb(168, 168, 168);
$c__default-dark: rgb(0, 0, 0);
$c__primary: #0da692;
$c__primary-light: #13ddc2;
$c__primary-dark: #0b7769;
$c__header-table: #f3f2f7;
//-Padding-
$pl__thead:1.5em;

// ---Table---
.tb-refactor {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
  margin: 3em;
  border-radius: 0.3em;
  box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.3);

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
  }
  .tb-refactor__menu__div2 {
    @extend .tb-refactor__menu__div;
    justify-content: flex-end;
  }
  // --Div-input adn icon---
  .tb-refactor__menu__div1__div-input {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
  }
  .tb-refactor__menu__div1__div-input > span {
    color: $c__default;
    margin-right: 0.5em;
  }
  .tb-refactor__menu__div1__div-input > i {
    color: $c__default-dark;
    font-size: 0.8em;
    margin-left: -1.5em;
    transition-duration: 200ms;
  }
  .tb-refactor__menu__div1__div-input_icon-active {
    transform: rotate(-180deg);
    transition-duration: 200ms;
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
    border-color: $c__primary;
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
  .tb-refactor__input__pag {
    @extend .tb-refactor__input;
    width: 5em;
  }
  .tb-refactor__input__search {
    @extend .tb-refactor__input;
    width: 60%;
  }
  // ---Thead---
  .tb-refactor__tb__thead {
    background-color: $c__header-table;
    text-align: start;
  }
    .tb-refactor__tb__thead > tr >th {
    padding-left: $pl__thead;
  }

  //---Tbody---
    .tb-refactor__tb__tbody {
    text-align: start;
  }
  .tb-refactor__tb__tbody > tr > td {
    padding-left: $pl__thead;
  }

}
</style>
