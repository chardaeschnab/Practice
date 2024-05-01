<template>
  <h1>Tic Tac Toe</h1>

  <div>Next turn: {{ turn ? "❌" : "⭕" }}</div>
  <div class="grid">
    <div v-for="(row, i) in grid" class="row">
      <div v-for="(val, j) in row" class="cell" @click="clickCell(i, j)">
        {{ val }}
      </div>
    </div>
  </div>
  <div v-if="win">{{ win }} win!</div>
</template>

<script>
export default {
  data() {
    return {
      grid: [
        [null, "❌", null],
        [null, null, null],
        [null, null, "⭕"],
      ],
      turn: true,
      win: null,
    };
  },
  methods: {
    clickCell(i, j) {
      //only if the cell is empty
      if (this.grid[i][j] === null) this.grid[i][j] = this.turn ? "❌" : "⭕";
      // change the turn
      this.turn = !this.turn;
      //check if somebody won
      this.checkWin();
    },

    //this method should check if somebody has 3 in a row
    // and if so, set the win variable to the player that won
    checkWin() {
      const firstRow =
        this.grid[0][0] === this.grid[0][1] &&
        this.grid[0][0] === this.grid[0][2];

      const secondRow =
        this.grid[1][0] === this.grid[1][1] &&
        this.grid[1][0] === this.grid[1][2];

      if (firstRow) {
        this.win = this.grid[0][0];
      } else if (secondRow) {
        this.win = this.grid[1][0];
      }
    },
  },
};
</script>

<style>
.cell {
  background-color: darkgrey;
  width: 70px;
  height: 70px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
}
.row {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}
.grid {
  display: grid;
  grid-template-rows: repeat (3, 1fr);
  gap: 10px;
}
</style>
