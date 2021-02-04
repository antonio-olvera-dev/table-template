<template>
  <div class="tb-refactor">
    <!-- ---Menu--- -->
    <div class="tb-refactor__menu">
      <div class="tb-refactor__menu__div1">
        <h1>1</h1>
      </div>
      <div class="tb-refactor__menu__div2">
        <h1>2</h1>
      </div>
    </div>

    <!-- ---Table--- -->
    <table class="table">
      <!-- ---Head--- -->

      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Handle</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td colspan="2">Larry the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
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
  .tb-refactor__menu__div {
    display: flex;
    width: 50%;
  }
  .tb-refactor__menu__div1 {
    @extend .tb-refactor__menu__div;
  }
  .tb-refactor__menu__div2 {
    @extend .tb-refactor__menu__div;
  }
}
</style>
